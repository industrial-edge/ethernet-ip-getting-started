# Configuration

- [Configuration](#configuration)
  - [Overview](#overview)
  - [Install Ethernet IP Connector](#install-ethernet-ip-connector)
  - [Configure Databus](#configure-Databus)
  - [Configure Ethernet IP via Common Configurator](#configure-ethernet-ip-via-Common-Configurator)

## Overview

When working with connectors on Industrial Edge, the **Databus** app is required to exchange the data via MQTT. The configuration of the connectors is done via the **Common Configurator** app. Therefore also the **IIH Registry Service** app is necessary, to find installed connectors on an Industrial Edge Device.

Make sure the following apps are installed and running on the Industrial Edge Device (IED):
- Databus
- Common Configurator
- IIH Registry Service

## Install Ethernet IP Connector

The Ethernet IP Connector app must be available in your IEM catalog. Proceed the following steps to install the app on your IED:

- open the catalog in the IEM
- select the Ethernet IP Connector
- click 'Install'
- in the tab 'Configurations' click 'Next'
- in the tab 'Devices' choose your IED
- click 'Install Now'
- click 'Install' to allow the installation

![app](/docs/graphics/EIP_App.png)

## Configure Databus

The system app Databus is essential to exchange data between a PLC and the IED. The Ethernet IP Connector sends the transfered data to the Databus on the IED. From there the data can be used for further processing.

You need to create a user and one or more topics in the Databus configuration, which cover the Ethernet IP data:

- ***ie/m/j/simatic/v1/eip1/dp*** for Ethernet IP metadata
- ***ie/d/j/simatic/v1/eip1/dp/#*** for Ethernet IP data

Therefore follow these steps:

- open the Industrial Edge Management (IEM)
- go to 'Data Connections' > Databus
- select the corresponding IED
- create the topic `ie/#`and a dedicated user with username and password ('edge'/'edge'), set permissions to 'Publish and Subscribe'
- deploy the configuration and wait for the job to be finished successfully

![databus](/docs/graphics/Databus.PNG)

## Configure Ethernet IP via Common Configurator

With the Common Configurator, you can configure several connectors and publish the data to the Databus. Therefore, you must enter the Databus credentials within the Common Configurator:

- open the IED web interface
- open the app Common Configurator
- go to the tab 'Settings' and select the menu 'Databus credentials'
- in the Common Configurator settings enter the databus service name: 'ie-databus:1883'
- in the Common Configurator settings under the tab 'Data Publisher settings' enter the databus user name and password ('edge'/'edge')
- in the Common Configurator settings under the tab 'Data Subscriber settings' enter the databus user name and password ('edge'/'edge')
- Save the settings

![IIH_Settings](/docs/graphics/Ccdatabus.PNG)

As soon as the Ethernet IP Connector is installed and started on the same IED as the Common Configurator, the connector is visible within the configurator. In this example we want to configure an EtherNet/IP connection to a CompactLogix PLC (Allen-Bradley). To configure the Ethernet IP Connector, proceed as following:

- go to the tab 'Get data' and select tab 'Connector Configuration'
- select the Ethernet IP Connector

![Cchome](/docs/graphics/Cchome.PNG) 

- switch to tab 'Tags'
- choose 'Add data source'

![Ccdatasources](/docs/graphics/Ccdatasources.PNG)

- configure the PLC accordingly and save

![Source](/docs/graphics/CCadddatasource.PNG) 

- under tab 'Tag' of the newly created PLC, choose 'Add tag'


![Source](/docs/graphics/Ccaddtag.PNG)

  
- configure a tag as needed and save

![Tags](/docs/graphics/IIH_Tags.png)

- select the newly created PLC and click 'Deploy'

![Deploy](/docs/graphics/IIH_Deploy.png)

- back on the overview page 'Available connectors', the status of the Ethernet IP Connector should be shown as **connected**

![Connected](/docs/graphics/IIH_Connected.png)

Now data can be transferred via the Ethernet IP connection. Please find more information in the  [Usage](/docs/Usage.md) documentation.
