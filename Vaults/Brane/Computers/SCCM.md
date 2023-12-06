Stands for System Center Configuration Manager

Uses [[MS active directory]] for security, service locations, configurations, and discover users/devices

Uses BITS and BranchCache to help manage network bandwidth
	Background Intelligent Transfer Service (BITS) facilitates transfer of files between a client and server. Also provides progress information. BITS allows an admin to set bandwidth maximums as well, allowing large file transfers to occur in the background while not handicapping network service to users.
	BranchCache is a WAN bandwidth optimizer included in Windows Server. 

Can also handle many other tasks:
Application management: Delegate rights to users to use different applications
Endpoint protection: Anti-malware, firewalls, etc
Inventory: Collect information about hardware, software, monitor license use, monitor user activity
OS Deployment: Create and deploy OS images
Software updates: Manage, deploy, monitor software updates (not just Windows OS, all applications)
	Recommendation is to cover the WSUS holes 
Reporting: Use SQL Server Reporting to provide reporting capabilities of inventory etc
Other uses include integrating with smart devices like light bulbs or whatever, or configuration of BYOD setups


