# CSCE 3530 Network Project

## Project Title
Project Book Club: Secure Hybrid Library Local Network Simulation

## Student
Fritzgerald Diabe

## Project Overview
This project simulates a secure hybrid local area network (LAN) designed for a community library called "Book Club" using Cisco Packet Tracer. The network integrates a central gateway router, a link-layer distribution switch, a wireless access point, a local multi-service data server, and multiple user endpoints. 

The Gateway Router provides core routing, dynamic host configuration, and Network Address Translation (NAT) between the internal library network and the external internet. The Library Data Server provides localized static DNS name resolution and hosts the digital library catalog web application via HTTP/HTTPS. The client endpoints—consisting of wired staff and public workstations alongside wireless guest devices—automatically request network parameters via DHCP, utilize the internal directory server for localized URL resolution, and access external internet nodes securely through address translation.

## Network Topology

| Device | Interface | IP Address | Purpose |
|---|---|---|---|
| Router0 | GigabitEthernet0/0/0 | DHCP (WAN) | Outside/Internet interface |
| Router0 | GigabitEthernet0/0/1 | 192.168.1.1/24 | Internal default gateway |
| Server0 | FastEthernet0 | 192.168.1.10/24 | Static Library Server (DHCP, DNS, HTTP) |
| PC0 | FastEthernet0 | 192.168.1.11/24 | Wired Staff Desktop client |
| PC1 | FastEthernet0 | 192.168.1.12/24 | Wired Public Lobby client |
| Laptop0 | Wireless0 | 192.168.1.13/24 | Wireless Guest BYOD client |

## Implemented Services

- DHCP dynamic allocations using Cisco IOS Pool scopes
- Localized Domain Name System (DNS) record mapping
- Embedded HTTP/HTTPS Web Server hosting the library catalog
- Dynamic NAT Overload (PAT) configuration via Cisco IOS Access Control Lists
- Wireless Link Layer bridging utilizing WPA2-PSK security
- ICMP end-to-end routing connectivity verification
- Local application-layer name resolution and web traffic testing

## 📁 Repository Directory Structure

```text
📦 bookclub-network-project
 ┣ 📂 design-files
 ┃ ┗ 📜 BookClub_Topology.pdf        <-- Main Cisco Packet Tracer project save file
 ┣ 📂 configuration-logs
 ┃ ┗ 📜 gateway_router_config.txt     <-- Saved Cisco IOS CLI running configuration
 ┣ 📂 documentation
 ┃ ┣ 📜 Project_Proposal.pdf          <-- Approved project proposal outline
 ┃ ┗ 📜 Final_Project_Report.pdf      <-- Comprehensive protocol analysis report
 ┗ 📜 README.md                       <-- Repository homepage and setup guide
