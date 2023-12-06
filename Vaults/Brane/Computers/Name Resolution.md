The process of converting human names and network addresses

Forward resolution converts names to addresses. (purdue.edu --> 128.210.7.200)
Reverse resolution goes from addresses to names

Common computer name spaces/domains:
	NetBIOS names for MS file and print sharing
	DNS names used for internet protocols and hosts (and [[MS active directory]])
	NetBIOS and DNS name are independent, but they ==should== be the same

The word *domain* does not describe anything specific or physical if there is not a modifier in front of it; e.g. DNS domain, Active Directory Domain, etc.

Hostname - the name of the computer; DNS rules say 255 chars max (e.g. Sam's MacBook Air)
Namespace - Name of a domain
	Logical set of hosts signified by a name controlled by a set of name servers. 

Fully Qualified Domain Name (FQDN) - the hostname appended to the namespace (EC01.example.com)
	

HOSTS file - a text file in windows computers that stores static maps of hostnames to IP addresses. Located in `C:\windows\system32\drivers\etc.

Name server - DNS server that resolves FQDNs to IP addresses
	They control namespaces for specified domains

DNS Name Space Structure
	hostname.subdomain(s).topleveldomain
	can go up to 127 deliminations, up to 63 characters per delimination
	authority flows from the top level to the lower levels
	ICANN manages root domains
		traditional - .edu, .com, .gov, .mil, .org, country codes

DNS Name Resolution
	IETF standard, starting from RFC 881
	Defines a hierarchical naming system
	Supports IP and IPX, IPX is dead now
	Computers cache DNS entries, so that they dont need to access a DNS server to resolve. To increase speed for a particular service, you can add it manually to the hosts file. 
	If there is bad information in the DNS cache, `ipconfig /flushdns` can clear the DNS cache on a windows machine.
	DNS does not have any security built into it, and it is vulnerable to many attacks, such as request spoofing, cache poisoning, and pharming.
	DNSSEC exists, but is not yet adopted in industry
	ARIN (American Registry for Internet Numbers) arin.net collects information and allows you to lookup owners of IP addresses
	DDNS (Dynamic DNS) is a method of updating name servers automatically

NetBIOS is an older part of Windows, but it's still around for workgroups
	Uses SMB/CIFS
	Supported over multiple layer three protocols: NetBIOS frames protocol, IPX/SPX, TCP/IP
	NetBIOS names are limited to 15 chars, and few symbols
	A 16th character is added to the end that denotes the service on the host that the name refers to
		00 - Workstation Service; 20 - Host Record (name); 1B - Domain Master Browser; 1C - Domain Controller
	Prior to [[MS active directory]], MS domains were NetBIOS based.
	MS AD natively uses DNS for name resolution now, but NetBIOS is still supported as a legacy solution
