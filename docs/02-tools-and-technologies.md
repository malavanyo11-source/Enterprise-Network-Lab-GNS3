# 2. Tools and Technologies

Here's everything being used to build this lab, and why each piece was chosen.

## Network Simulation

**GNS3 (Graphical Network Simulator-3)** — version 2.2.61

GNS3 was chosen over alternatives like Cisco Packet Tracer because it isn't a simplified simulator — it runs actual vendor operating systems (real Cisco IOS images, real FortiGate firmware, etc.) rather than an approximation of their behavior. This means the skills built here transfer directly to real hardware and real job environments.

## Virtualization

**VMware Workstation 17 Player**

GNS3 needs a virtualization engine to run its own management VM (the "GNS3 VM"), which handles the actual emulation of network devices. VMware was chosen over VirtualBox because it's generally recommended for best performance with GNS3, particularly for larger topologies.

## Routing and Switching

**Cisco IOS**

The industry standard for enterprise routing and switching. This forms the core layer of the lab.

## Firewall and Security

**Fortinet FortiGate**

Chosen specifically because FortiGate is widely used across many companies (not just large enterprises) and is known for its strong GUI-based management, in addition to its command line. This makes it a practical, high-value skill to develop alongside Cisco.

## Server Operating System

**Windows Server 2022**

Used to build out Active Directory Domain Services, DNS, and DHCP — the backbone services that almost every enterprise network depends on, regardless of which networking vendor is in use.

## Host Hardware

**Dell Precision 7530**
- 8th Gen Intel processor
- 32GB RAM
- SSD storage

This is a mobile workstation-class machine, which comfortably handles running multiple virtual routers, switches, a firewall, and a Windows Server VM simultaneously without performance issues.

---
[← Previous: Project Goal](01-project-goal.md) · [Back to README](../README.md) · [Next: Lab Environment Setup →](03-lab-environment-setup.md)
