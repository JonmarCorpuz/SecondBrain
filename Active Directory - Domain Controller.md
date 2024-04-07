A A Domain Controller (DC) is a server that serves as the central authority for authenticating and authorizing users and computers within a Windows domain network

* Authenticates users and computers when they attempt to log in to the domain
* Enforces security policies and permissions to determine what resources the authenticated users and computers are allowed to access within the domain
* Stores and hierarchically manages directory information (Ex: *User accounts*, *Group memberships*, *Computer accounts*, *OUs*, *etc.*)
* Replicates directory information with other Domain Controllers within the same domain to ensure consistency and fault tolerance (Allows changes made on one Domain Controller to be propagated to others, maintaining a consistent view of the directory services across the domain)
* Can host a copy of the global catalog, which contains a partial replica of all objects in the entire AD forest (The global catalog of a domain facilitates searching and locating objects across domains within the forest)
* Process Group Policy settings, which are used to define and enforce security and configuration settings for users and computers within the domain
* Establishes and maintains trust relationships with other domains and forests, allowing users in one domain to access resources in trusted domains
* Authenticates service requests within the same domain (Ex: *Requests for accessing shared resources, printers, or applications*, *etc.*)

* 
