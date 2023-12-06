As you grow more clients, it becomes more difficult to add a new one.

## System imaging
The process of making installer image files to standardize the process of onboarding a new client
Loads up a fresh install of any OS, similar to VMware templates.
Can sometimes require very specific hardware
Creating an image:
	1. Install the OS and all applications on a machine
	2. Prepare the system for imagine
		For windows, use `sysprep` utility to remove identifying information from the machine. Otherwise, all image-booted machines will have identical SIDs.
	3. Restart the system into its pre-installation environment
	4. Use imaging software to create the image
	5. Distribute the image to other machines and use imaging software to load it

Image distribution:
	Images can be copied using direct hard drive to hard drive copies
		Sometimes a manufacturer will do this for you if you buy enough machines. You send them an image, they load it on all of them.
	Can also be configured over the network, where a machine automatically configures to boot from an image on the network.
	Keeping hardware consistent will greatly reduce operating expenses