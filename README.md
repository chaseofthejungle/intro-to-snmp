# Intro to SNMP Overview Guide

**TODO:** A brief introductory guide to Simple Network Management Protocol (SNMP).

#### Table of Contents

1. [Defining SNMP](#define)
2. [SNMP Runtime Components](#components)
3. [Important SNMP Commands and Configurations](#commands)
4. [Limitations of SNMP](#limits)
5. [Supplemental Resources](#supplemental)

<hr />

## 1. <a name="define">Defining SNMP</a>

<hr />

## 2. <a name="components">SNMP Runtime Components</a>

* **SNMP-Managed Devices:** SNMP agents execute on a diversity of network devices (e.g., routers, switches, client workstations, printers), so that they may be monitored and managed. Through SNMP nodes, managed devices can interface with other components of a network.
* **SNMP Agents:** SNMP agents are software programs that execute on local devices and services that are being actively monitored, gathering data such as disk, CPU, and bandwidth usage. The SNMP manager/server quieries agents, which locate relevant data from storage and transmit data back to the requesting manager/server.  
* **SNMP Manager/Server:** This centralized management station executes the SNMP management app and interfaces with SNMP agents, prompting them to transmit back SNMP updates at specified/fixed intervals. It offers processing and memory resources needed to enable SNMP and keep it running.
* **Management Information Base (MIB):** These are text files (usually using `.mib` as an extension, but `.txt` and `.my` are also possible) that serve as collections of device/object information (listing data objects utilized by devices) that SNMP utilizes for network management (e.g., access control, querying). Managed devices are referenced using unique Object Identifiers (OIDs), which can be translated by SNMP into human-readable text that admins can consult.

<hr />

## 3. <a name="commands">Important SNMP Commands and Configurations</a>

<hr />

## 4. <a name="limits">Limitations of SNMP</a>

<hr />

## 5. <a name="supplemental">Supplemental Resources</a>

* *[Cisco Official SNMP Configuration Guide](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/snmp/configuration/xe-16/snmp-xe-16-book.html)*
* *[Aruba Official Configuring SNMP Guide](https://arubanetworking.hpe.com/techdocs/AOS-CX/10.07/HTML/5200-7887/Content/Chp_SNMP/cnf-snm.htm)*
* *[Configure SNMP in Junos OS (Official Juniper Guide)](https://www.juniper.net/documentation/us/en/software/junos/network-mgmt/topics/topic-map/configure-snmp-in-junos-os.html)*
