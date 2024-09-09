# Ethernet IP application example

This example provides a getting started guide, which shows how to use the Industrial Edge app Ethernet IP Connector.

- [Ethernet IP application example](#ethernet-ip-application-example)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [PLC project](#plc-project)
  - [Configuration](#configuration)
  - [Usage](#usage)
  - [Documentation](#documentation)
  - [Contribution](#contribution)
  - [Licence and Legal Information](#licence-and-legal-information)

## Description

### Overview

This tutorial shows how to use the Industrial Edge applications Ethernet IP Connector to establish a connection between an Industrial Edge Device (IED) and a 3rd party PLC that supports **EtherNet/IP**. These PLC variants are supported:

* Allen-Bradley ControlLogix (Rockwell)
* Allen-Bradley CompactLogix (Rockwell)
* Allen-Bradley MicroLogix (Rockwell)
* Allen-Bradley SLC (Rockwell)
* Omron CJ1 Series PLCs
* Omron CJ2 Series PLCs
* Omron CS1 Series PLCs

The Ethernet IP Connector is an application that runs on the individual IED. Connections can be configured using the Common Configurator for Industrial Edge. The connector transfers the value series of selected data points from a PLC to the Databus. From there the data can be used within other Edge apps, e.g. the Flow Creator.

### General task

Here we configure a connection to a CompactLogix PLC using the Ethernet IP Connector. The data is published on the Databus. By using the application Flow Creator, we fetch the metadata of the Ethernet IP Connector, write some data on the configured tags and read out the new data.

![Overview](/docs/graphics/EthernetIPArchi.PNG)

## Requirements

### Prerequisites

- Access to an Industrial Edge Management (IEM) with onboarded Industrial Edge Device (IED)
- IEM: Installed system configurator for Databus
- IED: Installed system app Databus
- IED: Installed app Ethernet IP Connector
- IED: Installed app IIH Registry Service
- IED: IIH Semantics
- IED: IIH Common Import Converter
- IED: Installed app Flow Creator
- IED is connected to the Rockwell PLC CompactLogix via Ethernet
- Studio 5000 project loaded on PLC
- Google Chrome (Version ≥ 72)

### Used components

- Industrial Edge Management (IEM) V1.16.11
  - Databus Configurator V3.0.0
- Industrial Edge Device (OS) V2.1.0-22
  - Databus V3.0.0
  - Common Configurator V1.11.1-0
  - Registry Service V1.11.0-2
  - Ethernet IP Connector V3.0.2-1
  - Flow Creator V1.17.1-1
  - IIH Essentials V1.11.0
- PLC: Allen-Bradley CompactLogix
- Studio 5000 Logix Designer V32.00

### PLC project

The used PLC project *Test.ACD* can be found in the [src folder](/src/).

## Configuration

You can find further information about the following steps in the [Configuration](/docs/Installation.md) documentation:

- [Overview](/docs/Installation.md#overview)
- [Install Ethernet IP Connector](/docs/Installation.md#install-ethernet-ip-connector)
- [Configure Databus](/docs/Installation.md#configure-databus)
- [Configure Ethernet IP via Common Configurator](/docs/Installation.md#configure-ethernet-ip-via-common-configurator)

## Usage

As soon as the Ethernet IP Connector is configured, data can be transfered.

You can find further information about how to handle the data via the Flow Creator in the [Usage](/docs/Usage.md) documentation:

* [Read metadata](/docs/Usage.md#read-metadata)
* [Write data](/docs/Usage.md#write-data)
* [Read data](/docs/Usage.md#read-data)
* [Use Data Service](/docs/Usage.md#use-data-service)

## Documentation

You can find further documentation and help in the following links

- [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
- [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
- [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
- [Industrial Edge GitHub page](https://github.com/industrial-edge)
  
## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you haven't previously signed the [Siemens Contributor License Agreement](https://cla-assistant.io/industrial-edge/) (CLA), the system will automatically prompt you to do so when you submit your Pull Request. This can be conveniently done through the CLA Assistant's online platform. Once the CLA is signed, your Pull Request will automatically be cleared and made ready for merging if all other test stages succeed.

## License and Legal Information

Please read the [Legal information](LICENSE.txt).
