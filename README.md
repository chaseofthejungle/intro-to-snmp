# Intro to SNMP Overview Guide

**Description/Overview:** Simple Network Management Protocol (SNMP) is the most widely-recognized network monitoring and mapping protocol, operating at the application layer. It is an industry-standard network communications solution for gathering and analyzing network traffic, generating: a) reports that administrators can consult to handle issues (such as network device outages/errors and performance bottlenecks), and b) real-time (noting changes as they occur) visual inventories of network connections and their connectivity statuses. SNMP was developed in the 1980s, with the current standard being SNMPv3.

#### Table of Contents

1. [Explaining SNMP](#explaining)
2. [SNMP Version History](#history)
3. [SNMP Runtime Components](#components)
4. [Important SNMP Commands and Messages](#commands)
5. [Limitations of SNMP](#limits)
6. [Supplemental Resources](#supplemental)

<hr />

## 1. <a name="explaining">Explaining SNMP</a>

Simple Network Management Protocol (SNMP) is a mechanism that serves as an 'essential service' for assuring networks are up, healthy, and performing as desired: in short, as ingress and egress traffic pass through networks, it needs to be monitored and responded to as necessary to assure availability, security, and high performance. SNMP is a request and response system that allows for such monitoring and requesting/responding to occur. Such characteristics as bandwidth, throughput, web server data request amounts and capacities (e.g., maximum transmission units of packets), and routing errors are tracked and handled as compromises and bottlenecks occur, as well as proactively. All network devices can be real-time queried/polled for performance, and should the thresholds of values (as configured administratively or by default) be surpassed, SNMP software agents will send alerts (for more information, see [Important SNMP Commands and Configurations](#commands) section).

SNMP operates by sending out messages known as Protocol Data Units (PDUs) to interfaces/devices within the network that are configured to respond to SNMP manager requests. The received data can be displayed (such as for purposes of network/system administrator consultation) or stored/logged (such as for the sake of scripting/documenting and backing up).

<hr />

## 2. <a name="history">SNMP Version History</a>

(TODO)

<hr />

## 3. <a name="components">SNMP Runtime Components</a>

* **SNMP-Managed Devices:** SNMP agents execute on a diversity of network devices (e.g., routers, switches, client workstations, printers), so that they may be monitored and managed. Through SNMP nodes, managed devices can interface with other components of a network.
* **SNMP Agents:** SNMP agents are software programs that execute on local devices and services that are being actively monitored, gathering data such as disk, CPU, and bandwidth usage. The SNMP manager/server quieries agents, which locate relevant data from storage and transmit data back to the requesting manager/server.  
* **SNMP Manager/Server:** This centralized management station executes the SNMP management app and interfaces with SNMP agents, prompting them to transmit back SNMP updates at specified/fixed intervals. It offers processing and memory resources needed to enable SNMP and keep it running.
* **Management Information Base (MIB):** These are text files (usually using `.mib` as an extension, but `.txt` and `.my` are also possible) that serve as collections of device/object information (listing data objects utilized by devices) that SNMP utilizes for network management (e.g., access control, querying). Managed devices are referenced using unique Object Identifiers (OIDs), which can be translated by SNMP into human-readable text that admins can consult.

<hr />

## 4. <a name="commands">Important SNMP Commands and Messages</a>

**Examples of five common messages/commands that enable interactions between SNMP managers and SNMP agents include:**

* *Trap (snmptrap Command):* Allows devices to send out alerts, in the form of asynchronous messages sent by managers to agents (such as when there is a need for a report, or just performing general monitoring/maintenance, such as verifying if idling devices are online). Traps may be sent in response to such events as increased traffic (scalability concerns), system boot up, and being unable to access previously used drives.
* *Get (snmpget Command):* Returns a single or multiple values from the Management Information Base (MIB).
* *Get Next (snmpgetnext Command):* Returns the next Object Identifier (OID) value in a MIB hierarchy/tree.
* *Set (snmpset command):* SNMP managers utilize these to direct SNMP agents to perform actions.
* *Get Response (GetResponse Messages):* Enables agents to return values quieried for by SNMP managers (through snmpget, snmpgetnext, and snmpset).

<hr />

## 5. <a name="limits">Limitations of SNMP</a>

**Some potential configuration-related drawbacks of SNMP include:**

* *High learning curve* for user account management/access control and encryption (e.g., AES, DES) and authentication (e.g., SHA, MD5) protocols.
* Increased possibility of *misconfigurations* due to human error, which can lead to security breaches due to improper or substandard enforcements (such as if complex password and/or password history policies are not being applied) and suboptimal resource utilization due to faulty monitoring processes.
  + There is also the issue of every SNMP device needed to have an unique engine ID configured for it. This introduces more potential for error because redundant interfaces may share these IDs. However, without them, devices may have important requests timeout or otherwise be declined. 

**Some potential performance-related drawbacks of SNMP include:**

* *Heavy processor burden* on network management station and endpoint devices, due to resource requirements of SNMP's encryption and authentication mechanisms.
* Load balancing needs due to *heavy network traffic*, as SNMP packets contain potentially large security headers that may not scale well on larger enterprise networks.
* *Request throughput bottlenecks*, as a consequence of high scaling on large networks (heavy monitoring and security related requests).

**Some additional security and support drawbacks of SNMP include:**

* *Susceptibility to spoofing and discovery message attacks* due to SNMP managers and agents not natively supporting robust authentication mechanisms (and, in the case of discovery messages, encryption mechanisms).
* *Lack of native compatibility with older SNMP versions*, because of modifications to message formatting and security mechanisms.
* Possibility of needing to purchase *paid support*, on a vendor-by-vendor and need-by-need (such as encryption and authentication) basis.
  
<hr />

## 6. <a name="supplemental">Supplemental Resources</a>

* *[Cisco Official SNMP Configuration Guide](https://www.cisco.com/c/en/us/td/docs/ios-xml/ios/snmp/configuration/xe-16/snmp-xe-16-book.html)*
* *[Aruba Official Configuring SNMP Guide](https://arubanetworking.hpe.com/techdocs/AOS-CX/10.07/HTML/5200-7887/Content/Chp_SNMP/cnf-snm.htm)*
* *[Configure SNMP in Junos OS (Official Juniper Guide)](https://www.juniper.net/documentation/us/en/software/junos/network-mgmt/topics/topic-map/configure-snmp-in-junos-os.html)*
