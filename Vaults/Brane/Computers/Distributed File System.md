Has two basic components: namespaces and replication
### Namespaces
Unified view of distributed file shares
Shares on distributed servers appear as if they are on the same server
Requires a namespace server, which maintains the namespace and defines the hierarchy. Uses the DFS Management tool. 
A single namespace can host files from any number of servers, but logically is the same as them being stored on one server
This is true for the user view as well; all files, regardless of the host server, have the appearance of being hosted on one server
	Simplifies browsing
For domain-based namespaces, follows the format `\\domainname\namespace`
Multiple namespaces can be made within a single domain. Each namespace is managed independently

### Replication
Two or more servers can host the same share, and automatically replicate the updates across each other
	Multiple benefits; geographic distribution, hierarchical control, redundancy, performance on large networks
Can be taxing on a network with large files across many replications, so there are a few controls admins have over replication parameters. For example, an admin can determine when a replication starts and set a maximum bandwith for it. 

DFS is site-aware, meaning it will use AD sites when determining where to seek for information to increase performance. 

### Implementation
Install DFS on servers
Choose a namespace server, use a DC if its domain-based
Create new DFS root
Create DFS folders
	Without targets for hierarchy
	With targets for data, multiple targets for targets that will be redirected
Define replication
	Create and configure DFS replication

Files in shares still use UNC. 