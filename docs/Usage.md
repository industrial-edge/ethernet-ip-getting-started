# Usage

- [Usage](#usage)
  - [Read metadata](#read-metadata)
  - [Read data](#read-data)
  - [Write data](#write-data)
  - [Use Data Service](#use-data-service)
  
Via the IE Flow Creator, we can write and read the EtherNet/IP data.

The used flow can be downloaded [here](/src/flow.json) and imported into the IE Flow Creator, that is running on the same IED as the Ethernet IP Connector.

## Read metadata

To print out the Ethernet IP Connector metadata, follow these steps:

- create a mqtt in node
- set the server to 'ie-databus' with port 1883 and corresponding user name/password ('edge'/'edge')
- set the topic to `ie/m/j/simatic/v1/eip1/dp`
- create a debug node and connecto to the mqtt in node
- deploy the flow and watch the debug window

![metadata_flow](/docs/graphics/Metadata_Flow.png)

![metadata](/docs/graphics/Metadata.png)

Now you can see the configured datapoint according to the Ethernet IP settings:

- ***Counter_INT*** with unique id 102
- ***Var_BOOL*** with unique id 103
- ***Var_REAL*** with unique id 104

## Read data

To print out the transfered Ethernet IP Connector data, follow these steps:

- create a mqtt in node
- set the server to "ie-databus" with port 1883 and corresponding user name/password ('edge'/'edge')
- set the topic to `ie/d/j/simatic/v1/eip1/dp/r/#`
- create a debug node and connecto to the mqtt in node
- deploy the flow
- as soon as the value for a configured tag changes, you can see it in the debug window

![read_data_flow](/docs/graphics/Read_Data_Flow.png)

Since the read payload only contains the tag ID and not the tag name, you need to assign the tag ID according to the metadata. Here the parameter ***Counter_INT*** (tag ID 102) is incremented automatically by the PLC, so we can read each single value:

![read_int](/docs/graphics/Read_Int.png)

## Write data

To write some data on the Ethernet IP tag, you must fetch the tag ID from metadata payload based on the tag name. Here we want to write to the parameter ***Var_REAL*** (tag ID 104). Please follow these steps:

- create an inject node with this JSON payload: `{ "vals": [ { "id": "104", "val": "111" } ] }`
- create a mqtt out node
- set the server to 'ie-databus' with port 1883 and corresponding user name/password ('edge'/'edge')
- set the topic to `ie/d/j/simatic/v1/eip1/dp/w/CompactLogix`
- connect the inject node to the mqtt out node
- deploy the flow
- click the inject button, to write the value

![write_data_flow](/docs/graphics/Write_Data_Flow.png)

![write_int](/docs/graphics/Write_Int.png)

## Use Data Service

The app Data Service collects the data out of different connectors and stores it for a defined time period. This is a prerequisite for other apps like Performance Insight.

To activate the data transfer from the Ethernet IP Connector, proceed as following:

- open the IED web interface
- open the app Data Service
- go to tab 'Connectors' and select 'Ethernet IP Connector'
- select the edit button and enter the user name and the password for the Databus user
- activate the adapter and save

![DataServiceAdapter](/docs/graphics/DataService_Adapter.png)

- go to tab 'Assets & Connectivity' and add the variables, that were configured within the Ethernet IP Connector

![DataServiceAdapter](/docs/graphics/DataService_Add.png)

- data is now collected by the Data Service and can be used by further apps
