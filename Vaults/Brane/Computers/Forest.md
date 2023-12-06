Defined by the X.500 directory framework as being the largest unit of organization for a directory. It is the entire directory for an organization.

A Forest is a single instance of [[MS active directory]]. It can contain one or multiple Domains. It is sometimes also called a security boundary. They are used to define the scope of authority of the administrators.
All domains within a forest, regardless of the domain tree they are part of, are trusted by each other from an authentication and authorization perspective
	This is because of trusts. Trusts can be configured between domains, but by default, transitive trust relationships are automatically created between parent and child domains. Transitive trust then flows upwards and is shared between all members of the forest unless manually configured otherwise. Trusts can also be configured to other trees or forests.

## Trees

A *domain tree* is a collection of one or more domains in the same forest that share a common namespace. For example, cit.purdue.edu and purdue.edu both exist under the same tree. 
## Domains

A domain is the next smallest unit of organization beneath a Forest. All objects on a Domain share the same Domain database. Changes are replicated across machines. 
They contain OUs, which themselves contain [[Windows Profiles]] and other domain objects.

### Sites

Sites are representation of the physical network topology. They theoretically exist beneath Domains, but serve a different purpose than Domains. Domains are administrative tools, whereas sites are network tools. Machines within a site will be communicating between each other much, much more than machines between sites. Sites determine the physical information flow between domain controllers. 

Sites should be created to organize machines into networking groups. Machines that are networked closely together should be bound to the same Site. Formally, Sites represent a TCP/IP subnet with highly reliable and fast network connections, likely over ethernet mediated by a controller or switch. 

Sites can be linked together. The links between sites will determine how replication and other information flows through the system. Because of this, it is important that sites are organized in such a way that optimizes network speed by minimizing the number of connections and the distance between those connections. Site links are transitive, meaning if site A and B are linked, and site B and C are linked, then sites A and C can communicate. 

Every domain has at least one Site. A default site called `Default-First-Site-Name` is created when a domain is created. 