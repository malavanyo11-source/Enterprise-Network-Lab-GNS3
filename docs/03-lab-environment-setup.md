# 3. Lab Environment Setup

Before any network topology could be built, the underlying GNS3 environment had to be installed and properly linked to its virtualization backend. This page documents that setup process.

## The Architecture: GNS3 Desktop + GNS3 VM

GNS3 uses a two-part architecture:

1. **GNS3 Desktop** — the graphical application installed directly on the host Windows PC. This is the drawing board and remote control — it's what you actually interact with.
2. **The GNS3 VM** — a dedicated Ubuntu Linux-based virtual machine that does the real work of emulating routers, switches, and firewalls. It runs inside VMware Workstation.

These two components talk to each other over a local network connection. The desktop app sends instructions; the VM executes them and runs the actual emulated devices.

## Setup Steps Completed

1. Installed GNS3 Desktop using the all-in-one Windows installer, selecting the default components (GNS3 Desktop, GNS3 VM, required runtimes)
2. Installed VMware Workstation 17 Player as the virtualization engine
3. Imported the GNS3 VM `.ova` file into VMware Workstation
4. Powered on the GNS3 VM and confirmed it booted correctly, displaying its assigned IP address on the console screen
5. Verified connectivity by accessing the GNS3 Web-UI directly at `http://<VM-IP-address>` from a browser on the host machine — confirming the VM's web server was reachable and responding
6. Ran the GNS3 Desktop Setup Wizard, selected VMware Workstation as the virtualization engine, and linked the desktop application to the running VM
7. Confirmed a fully live connection — both the local GNS3 server and the GNS3 VM showed green (connected) status in the Servers Summary panel, with real-time CPU and RAM statistics visible for both

## A Note on Troubleshooting

The connection between GNS3 Desktop and the GNS3 VM didn't work on the very first attempt — the VM showed as detected in the setup wizard, but stayed in a "not connected" (grey) state afterward.

The troubleshooting process involved:
- Confirming the VM was still powered on and healthy (checked via its console screen)
- Testing raw network connectivity by browsing directly to the VM's IP address, which confirmed the VM itself was working fine
- Refreshing the VM connection settings inside GNS3 Desktop's Preferences panel
- Restarting GNS3 Desktop entirely, which resolved the issue — both servers came up green immediately after reopening the application

This kind of troubleshooting — isolating whether an issue is on the client side, the network side, or the server side — is itself a core networking and IT support skill, and it's documented here as part of the honest build process, not just the polished end result.

## Result

With both servers connected, the lab environment is now fully operational and ready for device configuration — the next phase of this project.

---
[← Previous: Tools and Technologies](02-tools-and-technologies.md) · [Back to README](../README.md) · [Next: Network Architecture →](04-network-architecture.md)
