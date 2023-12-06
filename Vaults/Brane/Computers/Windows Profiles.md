A Profile is an environment created specifically for a user. Contains things like cookies, desktop, favorites, documents, start menu, etc.
Profiles are created for all new users based on a default profile that is copied and modified
	Default can be changed by administrator

Profiles are governed by 2 factors, rights and permissions.
	User rights are assigned to the user's profile and are things granted to them
	Permissions are assigned to objects, usually groups or OUs

Three types of profiles: 
### Local profiles
Basic type of profile scoped to a stand-alone computer. Typically stored at `C:\users\username
Not shared with other domain clients, which can make it very cumbersome in enterprise environments.
Most often used for individuals or for enterprise environments where each employee can be expected to stay on one computer
### Mandatory profiles
A read-only template profile assigned to an account is copied every time the user logs in, typically multiple accounts of users with the same use case (e.g. bank tellers). Changes are either not allowed or will not be saved the next time the user logs out and logs back in. Rarely used in technical positions. 
### Roaming profiles
Profile is stored on a network share, copied over to whatever machine they logon to. At logoff, the profile is copied back to the network share. 
Significantly increase logon/logoff time, especially if the user is using large files. 
Dependent on server functionality
Can create versioning issues if the user logs into multiple computers simultaneously
Copy of the profile remains on the local machine after logoff. Cached security credentials could remain, and another equipped enough user could potentially steal this information
To configure a roaming profile, specify the UNC of the profile's home directory path to be inside a network share

### Folder Redirection
Portions of the profile can be redirected. Redirected components are *not* copied at logon/logoff, they are saved directly to wherever they are redirected to in real time.
Not necessarily redirected to a network share, but usually.
Can reduce logon times, increase security by reducing data left on clients
Allows for a mix between mandatory and roaming profile approaches