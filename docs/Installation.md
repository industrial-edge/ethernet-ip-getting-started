# Configuration

- [Configuration](#configuration)
  - [Overview](#overview)
  - [Install Ethernet IP Connector](#install-ethernet-ip-connector)
  - [Configure IE Databus](#configure-ie-databus)
  - [Configure IIH Configurator](#configure-iih-configurator)
  - [Configure Ethernet IP Connector](#configure-ethernet-ip-connector)

## Overview

When working with connectors on Industrial Edge, the **IE Databus** app is required to exchange the data via MQTT. The configuration of the connectors is done via the **IIH Configurator** app. Therefore also the **Registry Service** app is necessary.

Make sure the following apps are installed and running on the Industrial Edge Device (IED):
- IE Databus
- IIH Configurator
- Registry Service

## Install Ethernet IP Connector

The Ethernet IP Connector app must be available in your IEM catalog. Proceed the following steps to install the app on your IED:

- open the catalog in the IEM
- select the Ethernet IP Connector
- click 'Install'
- in the tab 'Configurations' click 'Next'
- in the tab 'Devices' choose your IED
- click 'Install Now'
- click 'Install' to allow the installation

## Configure IE Databus

The system app Databus is essential to exchange data between a PLC and the IED. The Ethernet IP Connector sends the transfered data to the Databus on the IED. From there the data can be used for further processing.

You need to create a user and one or more topics in the Databus configuration, which cover the Ethernet IP data:

- ***ie/m/j/simatic/v1/eip1/dp*** for Ethernet IP metadata
- ***ie/d/j/simatic/v1/eip1/dp*** for Ethernet IP data

Therefore follow these steps:

- open the Industrial Edge Management (IEM)
- go to "Data Connections" > IE Databus
- select the corresponding IED
- create the topic `"ie/#"`and a dedicated user with username and password ("edge"/"edge"), set permissions to "Publish and Subscribe"
- deploy the configuration and wait for the job to be finished successfully

![databus](/docs/graphics/Databus.png)

## Configure IIH Configurator

- open the IED web interface
- open the app IIH Configurator
- go to the tab 'Settings'
- enter the databus service name: 'ie-databus:1883'
- in tab 'Data Publisher settings' enter the databus user name and password ('edge'/'edge')
- in tab 'Data Subscriber settings' enter the databus user name and password ('edge'/'edge')
- Save the settings

![IIH_Settings](/docs/graphics/IIH_Settings.png)

- go to the tab 'Aggregate data' and select tab 'Databus connectors'
- **TODO**

## Configure Ethernet IP Connector

**TODO**

To use the app Ethernet IP Connector properly (which has no web ui), the corresponding app Ethernet IP Configurator is necessary.
Here the connection to the Rockwell PLC can be configured.

- Open the Industrial Edge Device web interface
- Make sure that the app Ethernet IP Connector is running
- Open the app Ethernet IP Configurator
- Add the Rockwell PLC as data source

![Source](/docs/graphics/ethernet_ip_source.png)

- Configure the user settings
  
![Settings](graphics/ethernet_ip_settings.png)

- Add all needed tags

![Tags](/docs/graphics/ethernet_ip_tags.png)

- Deploy the configuration
- Start the project

![Connectors_overview](/docs/graphics/connectors_overview.png)
