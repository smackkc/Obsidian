AD is Microsoft's network directory service. It is a central repository of networked devices, information, users, querying information, updating, and authenticating against the data. Dependent on DNS (Domain Name Service)

Workgroups allow two Windows computers to connect in a minimal way to share files and resources. It is the lowest tier of Windows AD service. Domains are not joined, and there is no dependencies between the computers.

Domain - collection of objects that share the same database. 

*Sites* represent the physical structure (or topology) of your network. 
	A site is a collection of well-connected subnets. 
		Branch offices might be created as a site
		In AD, subnets determine the relative location of an item in the directory.
			What server should a client authenticate against?
Replication is complicated
	Changes performed on one domain controller are copied over to the others. 
	On the same site, replication will happen within 15 seconds. Across sites, it can take between 15 and 180 minutes. 
Everything in an AD is an object. Objects are instances of classes. 255 blah blah. 
	Schema holds the classes for the objects you create. 
	Group policy objects (GPO) and organizational units are used to configure settings for users and computers
		Organizational units are used to contain specific objects within a policy you wish to enforce among those objects.
			E.x. Student users (OU) cannot install programs (policy)
		Allows higher granularity and hierarchy structure
OUs have two main uses.
	To link GPOs
	Delegation of control

Forest
	A forest is a single instance of Active Directory
	Within a forest you can have one or multiple domains that share the same schema
	Smallest possible forest contains a single domain controller (DC)
	Also called a *security boundary*. 
	Forests contain domains, domains contain OUs, OUs contain objects (users, computers, devices)
	Transitive trusts are created when there are multiple domains within a forest made of multiple domain trees. Can be configured, in some cases are required to be configured.

FSMO roles
	Flexible Single Master Operator designated to single servers
	Schema Master - The DC that is allowed to make changes for the schema (definitions of things in the database). Only one in the entire forest.
	Domain Naming Master - The DC responsible for the forest-wide namespace. Must be on a DC that is also a Global Catalog Server
	PDC Emulator - Used for packward copatibility with Windows NT DCs and for propagating password changes quickly across all DCs in the domain (seconds, not hours). Should not be the same machine as Global Catalog, ideally.
	RID Master - Responsible for making sure that SIDs are unique within the domain - SID is long security ID. All SIDs in a domain are the same up to the last 32 