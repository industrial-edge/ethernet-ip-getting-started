# Ethernet IP application example

This example provides a getting started guide, which shows how to use the Industrial Edge app Ethernet IP Connector.

- [Ethernet IP application example](#ethernet-ip-application-example)
  - [Description](#description)
    - [Overview](#overview)
    - [General task](#general-task)
  - [Requirements](#requirements)
    - [Prerequisites](#prerequisites)
    - [Used components](#used-components)
    - [Studio 5000 Logix Designer Project](#studio-5000-logix-designer-project)
  - [Configuration steps](#configuration-steps)
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

Here we configure a connection to a CompactLogix PLC using the Ethernet IP Connector. The data is published on the IE Databus. By using the application IE Flow Creator, we fetch the metadata of the Ethernet IP Connector, write some data on the configured tags and read out the new data.

![Overview](/docs/graphics/overview-eip.png)

## Requirements

### Prerequisites

- Access to an Industrial Edge Management (IEM) with onboarded Industrial Edge Device (IED)
- IEM: Installed system configurator for Databus
- IED: Installed system app Databus
- IED: Installed app Ethernet IP Connector
- IED: Installed app IE Flow Creator
- IED is connected to the Rockwell PLC CompactLogix via Ethernet
- Studio 5000 project loaded on PLC
- Google Chrome (Version ≥ 72)

### Used components

- Industrial Edge Management (IEM) V 1.5.1-4 / V 1.8.6
  - IE Databus Configurator V 1.7.8
- Industrial Edge Device (OS) V 1.8.0-6
  - IE Databus V 1.7.1
  - Ethernet IP Connector V 2.0.0-5
  - IE Flow Creator V 1.3.9
- PLC: Allen-Bradley CompactLogix
- Studio 5000 Logix Designer V 32.00

### Studio 5000 Logix Designer Project

The used TIA Portal project can be found in the [sources folder](/src) under the following name:

[compactlogix-demo-29042021.7z](./src/compactlogix-demo-29042021.7z)

## Configuration steps

You can find further information about the following steps in the [Configuration](/docs/Installation.md) documentation.

- Configure PLC Connection (Databus, EthernetIP Connector)
- Configure Configure Data Service
- Configure Performance Insight

## Usage

Once the Data Service app is configured and data is availalbe from a running Rockwell PLC, process data can be collected. Performance Insight visualizes this data and gives data insights (KPIs, metrics, etc.).

## Documentation

You can find further documentation and help in the following links

- [Industrial Edge Hub](https://iehub.eu1.edge.siemens.cloud/#/documentation)
- [Industrial Edge Forum](https://www.siemens.com/industrial-edge-forum)
- [Industrial Edge landing page](https://new.siemens.com/global/en/products/automation/topic-areas/industrial-edge/simatic-edge.html)
- [Industrial Edge GitHub page](https://github.com/industrial-edge)
  
## Contribution

Thank you for your interest in contributing. Anybody is free to report bugs, unclear documentation, and other problems regarding this repository in the Issues section.
Additionally everybody is free to propose any changes to this repository using Pull Requests.

If you are interested in contributing via Pull Request, please check the [Contribution License Agreement](Siemens_CLA_1.1.pdf) and forward a signed copy to [industrialedge.industry@siemens.com](mailto:industrialedge.industry@siemens.com?subject=CLA%20Agreement%20Industrial-Edge).

## Licence and Legal Information

Please read the [Legal information](./LICENSE.md).
