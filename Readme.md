# Koray Erek - Enterprise Campus

## Overview
In this project, I built a two-site enterprise campus network in Cisco Packet Tracer to simulate an HQ and Branch office environment. I wanted to practice switching, routing, redundancy, segmentation, DHCP, ACLs, and basic wireless management in a more realistic enterprise-style topology instead of doing only small isolated labs.

## Project Goals
The main goals of this lab were:
- build a realistic HQ and Branch topology
- segment the network with VLANs
- add Layer 2 redundancy at the distribution layer
- use dynamic routing between sites
- provide centralized DHCP
- control user access to remote server networks
- simulate management Wi-Fi at both sites
- validate internet-edge NAT/PAT behavior

## Topology Summary
The network includes:
- 1 HQ site
- 1 Branch site
- redundant distribution switches
- access switches for end devices
- local servers and printers at both sites
- inter-site routing between HQ and Branch
- management wireless access
- dual-ISP edge design at HQ

## Technologies Used
- VLANs
- 802.1Q Trunking
- EtherChannel
- Spanning Tree Protocol (STP)
- SVI-based Inter-VLAN Routing
- HSRP
- OSPF
- DHCP
- DHCP Relay
- ACLs
- NAT/PAT
- WLC and Lightweight APs

## VLAN and IP Plan

### HQ
- VLAN 10 - Users - 10.10.1.0/24
- VLAN 20 - Voice - 10.10.2.0/24
- VLAN 30 - Corp Wi-Fi (planned) - 10.10.3.0/24
- VLAN 40 - Guest Wi-Fi (planned) - 10.10.4.0/24
- VLAN 50 - Servers - 10.10.5.0/24
- VLAN 60 - Printers - 10.10.6.0/24
- VLAN 99 - Management - 10.10.7.0/24
- VLAN 999 - Native/Unused

### Branch
- VLAN 110 - Users - 10.20.1.0/24
- VLAN 120 - Voice - 10.20.2.0/24
- VLAN 130 - Corp Wi-Fi (planned) - 10.20.3.0/24
- VLAN 140 - Guest Wi-Fi (planned) - 10.20.4.0/24
- VLAN 150 - Servers - 10.20.5.0/24
- VLAN 160 - Printers - 10.20.6.0/24
- VLAN 199 - Management - 10.20.7.0/24
- VLAN 999 - Native/Unused

## What I Implemented
In this lab, I implemented:
- VLAN-based segmentation for users, voice, servers, printers, and management
- trunk links between access and distribution switches
- EtherChannel between distribution switches
- STP root placement for better Layer 2 path control
- HSRP for gateway redundancy
- OSPF routing between HQ and Branch
- centralized DHCP with helper addresses
- ACLs to stop HQ users from reaching Branch server networks and Branch users from reaching HQ server networks
- management Wi-Fi at both HQ and Branch
- dual-ISP internet edge design with NAT/PAT validation

## Validation
I successfully tested the following:
- end devices received IP addresses through DHCP
- inter-VLAN communication worked
- HQ and Branch routed traffic through OSPF
- HSRP gateway behavior worked correctly
- ACL-based restrictions worked as expected
- HQ and Branch management Wi-Fi clients connected successfully
- NAT/PAT translations were visible at the internet edge

## Notes
This project was built in Cisco Packet Tracer, so some firewall and advanced wireless behaviors were limited by the simulator. Because of that, the main focus of this project was the enterprise campus design itself: switching, routing, redundancy, DHCP, ACLs, and end-user connectivity.

## What I Learned
This project helped me understand how Layer 2 redundancy, first-hop redundancy, and Layer 3 routing work together in an enterprise network. It also helped me get more comfortable with IP planning, OSPF path design, DHCP relay, ACL placement, and multi-site connectivity.

## Files
- `Koray_Erek_Enterprise_Campus.pkt`
- `Koray_Erek_Enterprise_Campus.png`