# Usage

- [Usage](#usage)
  - [Read metadata](#read-metadata)
  - [Write data](#write-data)
  - [Read data](#read-data)
  - [Use Data Service](#use-data-service)
  
Via the IE Flow Creator, we can write and read the Ethernet IP data.

The used flow can be downloaded [here](/src/flow.json) and imported into the IE Flow Creator, that is running on the same IED as the Ethernet IP connector.

## Read metadata

To print out the Ethernet IP Connector metadata, follow these steps:

- create a mqtt in node
- set the server to "ie-databus" with port 1883 and corresponding user name/password ("edge"/"edge")
- set the topic to `ie/m/j/simatic/v1/eip1/dp`
- create a debug node and connecto to the mqtt in node
- deploy the flow and watch the debug window

![metadata_flow](/docs/graphics/Metadata_Flow.png)

![metadata](/docs/graphics/Metadata.png)

Now you can see these configured datapoints according to the Ethernet IP settings:

- ***xx*** with unique id 101 **TODO**
- ***xx*** with unique id 102 **TODO**

## Write data

To write some data on the Ethernet IP tags, you must fetch the tag ID from metadata payload based on the tag name. Please follow these steps:

- for the ***xx*** tag, create an inject node with this JSON payload: `{ "vals": [ { "id": "101", "val": "true" } ] }` **TODO**
- for the ***xx*** tag, create an inject node with this JSON payload: `{ "vals": [ { "id": "102", "val": "111" } ] }` **TODO**
- create a mqtt out node
- set the server to "ie-databus" with port 1883 and corresponding user name/password ("edge"/"edge")
- set the topic to `ie/d/j/simatic/v1/eip1/dp/w/xxx` **TODO**
- connect all inject nodes to the mqtt out node
- deploy the flow
- click the single inject buttons, to write the values

![write_data_flow](/docs/graphics/Write_Data_Flow.png)

## Read data

To print out the transfered Ethernet IP Connector data, you must fetch the tag ID from metadata payload based on the tag name. Please follow these steps:

- create a mqtt in node
- set the server to "ie-databus" with port 1883 and corresponding user name/password ("edge"/"edge")
- set the topic to `ie/d/j/simatic/v1/eip1/dp/r/#` **TODO**
- create a debug node and connecto to the mqtt in node
- deploy the flow
- as soon as the value for a configured tag changes, you can see it in the debug window

![read_data_flow](/docs/graphics/Read_Data_Flow.png)

Output for tag ***Bool*** with ID 102: **TODO**

![read_bool](/docs/graphics/Read_Bool.png)

Output for tag ***Int*** with ID 103: **TODO**

![read_int](/docs/graphics/Read_Int.png)

## Use Data Service

 **TODO**
 
The app Data Service collects the data out of the Ethernet IP Connector and stores it for a defined time period.
This is a prerequisite for other apps like Performance Insight.

- Open the Industrial Edge Device web interface
- Open the app Data Service
- Go to the adapter settings and select "Ethernet IP Connector"
- Enter the username and password for the databus user
- Activate the adapter

![DataServiceAdapter](/docs/graphics/DataService_Adapter.png)

- Go to the assets view and add new variables for data, comming from the Ethernet IP Connector

![DataServiceAdapter](/docs/graphics/DataService_Add.png)

![DataServiceAdapter](/docs/graphics/DataService_Variables.png)

