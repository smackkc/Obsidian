Block device - physical hard drive
File containers - logical device, formatted partition

Network attacheed storage (NAS)
	File storage available over a network
	Ethernet is the most common transportation medium, but no specific hardware required
	Storage area networks (SAN) - block level storage accessible over a network. Uses dedicated hardware to interconnect the storage arrays. SAN storage appears as blank drives to clients. Must partition before use.

Partitions
	OS may create a partition called a "swap" partition, which is a temporary partition that uses system storage as backup RAM.
	System partition - contains OS fields and files needed for booting. Will remain active.
		Intel x86 systems boot from the Master Boot record (MBR). MBR is stored in the boot sector and tells where to find boot files. It transfers control to NT Loader, which executes and figures out where the files are. 
	Data partition - Optional way of organizing data into different partitions
	Windows typically uses one partition for everything, which is bad

Windows file systems have progressed from FAT16, FAT32, and now to NTFS. FAT has been discontinued except for in the form of exFAT, which is used for removable media such as USB drives or DVDs. This is because NTFS has too much security built in for the convenient use case of removable media. A USB stick flashed with NTFS will only be usable on the machine that flashed it.

## Connector types
ATA (AT Attachment) - Uses 50-pin ribbon cable to connect hard drives. Uses IDE,EIDE, and Ultra-ATA standards.

SATA (Serial ATA) - Provides more bandwidth, higher speed, and smaller footprint than ATA.

SCSI ( Small Computer System Interface)

## Layers and Hierarchies
Drive - Physical storage medium
Disk controller - Controls read/write from/to drives. All transactions originated by the controller. Controller by the processor.
RAID - Can be used to aggregate multiple drives into a single, fault tolerant, higher performance storage device. An entire RAID array is viewed as a single storage block device by higher layers.
	Operations are handled by a separate hardware XOR engine. It does not use the processor at all. However, this creates a single point of failure.
	RAID Types
		RAID 0 - Data is distributed across multiple disks. Increases performance, but no redundancy. 
		RAID 1 (Mirroring) - Data duplicated across multiple disks. Increases redundancy, but doesn't increase performance. Fault tolerant.
		RAID 5 (Striped) - Data is striped across multiple disks. Increases performance. Parity data kept over multiple drives. Provides some redundancy.
		RAID 10 or 1+0 - Stripes data across multiple disks, and then mirrors them. Less performance but more fault tolerance than RAID 5.