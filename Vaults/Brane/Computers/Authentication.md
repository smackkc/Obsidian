answering the question, who are you?
3 mechanisms:
	knowledge - some kind of information that only one person knows, such as a password, PIN, answers to questions, etc.
	ownership - smart card, key, badge, phone
	characteristics - biometrics, signature, keystroke pattern, gait

location is also used for some services

passwords have user-associated insecurities
	short ones are easily cracked by brute-force attack
	people are bad at keeping them secret
this can create an environment where its safest to enable certain restrictions on password logins, such as lockouts, auditing logon events (part of good [[Accounting]]), or minimum password lengths

*federated access* is a single sign-on (SSO) strategy that allows multiple systems or applications to be authenticated with one credential. requires a lot of technical agreement and collaboration between applications/networks

identity federation is the technology, standards, policies, and processes that allow an organization to trust digital identities, identity attributes, and credentials created and issued by another organization

OpenID is an open standard that allows users to be authenticated by certain cooperating sites usign a third party service
Open Identity Trust Framework is a set of specifications of a trust framework for identity and attribute exchange, developed jointly by OIDF and ICF (Information Card Foundation, another nonprofit thing)
Open Identity Exchange (OIX) is a corporation that provides certificates of trust frameworks that abide by the OITF
OAuth is an authorization standard developed by Twitter but used open-source by many websites that enables federated access using OID for authentication. 
	Any time there's "Sign in with google" or whatever, it's OAuth

OpenID Connect (OIDC) is an authentication protocol that is developed by OIDF and follows the OID standard. It uses OAuth2.0 to authorize. It is used for many web services, such as Microsoft, Google, Paypal, and Amazon.