# Configuration

- [Configuration](#configuration)
  - [Configure PLC Connection](#configure-plc-connection)
    - [Configure Databus](#configure-databus)
    - [Configure Ethernet IP Connector](#configure-ethernet-ip-connector)
  - [Configure Data Service](#configure-data-service)
  - [Configure Performance Insight](#configure-performance-insight)

## Configure PLC Connection

To read data from a Rockwell PLC and provide the data, we will use the Ethernet IP Connector to establish a connection with the PLC.
The Ethernet IP Connector sends data to the Databus from where the Data Service can collect and save the needed values.
In order to build this infrastructure, these apps must be configured properly:

- Databus
- Ethernet IP Connector

### Configure Databus

- Open the Industrial Edge Management web interface
- Go to "Data Connections" > IE Databus
- Select the corresponding Industrial Edge Device
- Create a new user with username and password and give the user publish and subscribe permission
- Create this topic `"ie/#"`
- Deploy the databus configuration and wait for the job to be finished successfully

![Databus](docs/graphics/Databus.png)

### Configure Ethernet IP Connector

- Open the Industrial Edge Device web interface
- Open the Ethernet IP Configurator
- xxx
- Open the Ethernet IP Connector
- xxx

## Configure Data Service

- Open the Industrial Edge Device web interface
- Open the Data Service
- Go to the adapter settings and select "Ethernet IP Connector"
- xxx

## Configure Performance Insight

xxx
