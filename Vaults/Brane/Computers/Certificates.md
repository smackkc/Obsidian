X.509 is the most widely accepted format for public-key certificates. It is specified in RFC 5280. 

Certificates are used in most network security applications, such as IPSEC, SSL, S/MIME, HTTPS, etc.

Public-Key Infrastructure (PKI) is all the hardware, software, people, and policies required to make public-key digital certificates

**Trust store** - A list of Certificate Authorities (CAs) and their public keys

Challenges:
	Users rely on certificates to inform decisions
	Not all CAs in the trust store are equally trustable
	Different browsers and OS can use different trust stores
