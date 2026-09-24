# 4. Network Architecture

This page outlines the planned topology for the enterprise lab — the design decisions behind it, and how the different vendor systems will interact.

## High-Level Design

The network is structured in layers, mirroring how real enterprise networks are typically designed:

### Core Layer
Cisco IOS routers and switches handle the backbone of the network — routing between subnets, VLAN segmentation, and inter-VLAN routing. This layer represents the traditional "plumbing" of the network.

### Security Layer
A FortiGate firewall sits at the boundary between network segments, enforcing security policies. Planned configurations include:
- Defined security zones (e.g. internal, DMZ, guest)
- Firewall policies controlling traffic between zones
- A site-to-site VPN tunnel, to simulate connecting two office locations securely

### Services Layer
Windows Server 2022 provides the services that make the network actually usable day to day:
- Active Directory Domain Services, for centralized user and device management
- DNS, for internal name resolution
- DHCP, for automatic IP address assignment to clients

### Client Layer
End-user virtual machines will join the Active Directory domain and receive their network configuration automatically via DHCP, simulating how real end-user devices behave inside an enterprise network.

## Design Philosophy

Rather than just connecting devices together for the sake of it, each design decision in this lab is meant to reflect a real business justification:

- VLANs exist to separate traffic types (e.g. servers, users, guests) for both performance and security reasons
- The firewall exists to enforce that not all traffic should freely flow between segments
- Active Directory exists because manually managing user accounts and permissions on every single machine doesn't scale
- DHCP and DNS exist because manually configuring IP addresses and hostnames on every device is impractical at any real scale

## What This Section Will Include As It Develops

- A visual topology diagram
- IP addressing scheme and VLAN plan
- Router and switch configuration files
- FortiGate firewall policy configuration
- Screenshots of traffic flowing correctly between segments

---
[← Previous: Lab Environment Setup](03-lab-environment-setup.md) · [Back to README](../README.md) · [Next: Skills Demonstrated →](05-skills-demonstrated.md)
