2 fundamental kinds
Client-Based (Hosted) Architecture
	The virtualization layer sits atop the original native OS, and other OS applications can run alongside it.

Bare-metal (Hypervisor) Architecture
	Virtualization layer sits atop the hardware, and all OS on the machine sits on top of the virtualization layer
	More efficient

## Advantages of VMs
VMs can easily be cloned or used as templates
They can run many different operating systems on the same hardware
Quickly create test environments
Increases reliability by increasing modularity. If a portion of a server fails, other less used portions of the server can quickly be repurposed to restore functionality.

## Implementation
VMWare is the most common software suite used to implement virtualization. It is the market leader, being practically the only option in the market.
ESXi server is a free download and provides the most needed functionality

vSphere is a suite of software/services to manage VMs
	Hypervisor (ESX, ESXi)
		vCenter Server enables management of machines and servers
	vMotion and Storage vMotion offers the ability to move running VMs between servers
	VMware DRS (Distributed Resource Scheduler) allocates resources across VMs on an as-needed and real-time basis
	VMware HA (High Availability) and FT (Fault Tolerance) offers automatic failover protection for VMs during server failures.

Define the hostname and IP address in DNS manager before installing vCenter

## Application & Desktop Virtualization
Individual resources can be virtualized without virtualizing the entire platform
Typical OS does this all the time, things like virtual memory
