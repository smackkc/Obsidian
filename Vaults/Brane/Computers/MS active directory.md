==Do not transfer the PDC Emulator in any case in lab. Industry is different==

Users are created within a specific domain and can authenticate against any DC within that domain
	Kerberos is used by default for authentication
	One user can be part of multiple groups. They will get a new SID on their security token for every group they're added to.

Two types of groups:
	Security groups have SIDs added to user tokens and can be used in ACLs
	Distribution groups do not have any security features and are for organization only (typically messaging)


A schema defines the attribute types a directory can contain as well as the structure of the database

## FSMO
Flexible Single Master Operator roles are roles assigned to specific computers within a domain that serve broader purposes for the entire domain and/or forest. There are 5. Ideally, they would all be assigned to separate servers. 
1. Schema Master (Forest-wide): Domain controller that records schema structure and is allowed to make changes to it. Only one in the entire forest.
2. Domain Naming Master (Forest-wide): Domain controller responsible for accounting the forest-wide namespace. Must be the DC that is also a Global Catalog Server. Can typically be offline without serious consequences. 
3. PDC Emulator (Domain-wide): Enables backward compatibility with Windows NT DCs, & for propagating password changes quickly across all DCs in the domain. Should *not* be the same machine as Global Catalog. Cannot go offline during business hours without serious consequences. 
4. Relative ID Master (Domain-wide): Ensures long security IDs are unique within a domain
5. Infrastructure Master (Domain-wide): Maintains references to objects located in other domains (phantoms). Also, updates other domains about changes in the local domain. 

In a multi-domain forest, at least one DC must be configured as a global catalog server. A global catalog server lists all objects in the forest. In a single-domain forest, all DCs should be Global Catalog Servers so that the domain remains fully functional if one DC fails. 

Roles are assigned automatically. They first exist where they are created, on the first DC. They can also be transferred or seized. If an FSMO role is seized from a device, the device is disowned from the domain. 
Moving can be necessary for performance, fault tolerance, or upgrades.
Seizures should only be used when the server is inaccessible. A server that has had an FSMO role seized from it should ==never== be brought back online before reformatting. 
## Kerberos
Kerberos is an [[authentication]] method used by MS AD. 

# Enterprise

Subnets - Logical representation of IP subnets in the environment
	Used to determine relative location of an item in the directory
		ex: what server should a client authenticate against?

Sites - One or more interconnected subnets
	Used for DC replication
	Represent the physical structure of the network
	Enables the client to access the DC that is physically closest
	Typically connected via a slower (WAN) network
	A Domain may span multiple sites, and a site may span multiple domains
	Sets up redundant paths between DCs
	Makes replication more efficient by multiple mechanisms; bridgeheads, more information about locations, handles authentication, 

Can have multiple subnets in a site, but cannot have multiple sites in a subnet

In a multi-domain forest, at least one DC must be configured as a global catalog server, which maintains information about all objects in the directory. Should be assigned to a different DC than the PDC emulator. Leaf objects are exempt, they are stored on the DCs responsible for a single domain. 

#### Single v. Multi Master

AD is generally a multi-master database
	Changes can be made on any DC and then replicated
	Conflicts can arise when changes made on multiple DCs
		Typically resolved via "last writer wins"

Some functions are critical enough to warrant single-master operations, covered above in FSMO.
Forest wide roles should never be assigned to the DC that is the Global Catalog Server. Domain specific roles can stay on the first DC in the domain as long as it's not a GC server.

Can also consider setting up standby operations master DCs.
