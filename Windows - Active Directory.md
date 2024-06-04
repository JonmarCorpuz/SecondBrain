
# Forest Structure

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/ad_forest_img1.jpg)

## Forest

A forest in Active Directory is a collection of one or more domains that share a common schema, configuration, and global catalog

* Serves as the top-level container within the Active Directory hierarchy
* Represents a security and administrative boundary for an organization's network infrastructure

## Tree

A tree in Active Directory refers to a hierarchical arrangement of domains within a single forest

* Forms a logical hierarchy, with domains organized in a parent-child relationship, where child domains are subdomains of their parent domains

## Domain

A domain in Active Directory is a logical grouping of network objects that share a common directory database and security policies

* Serves as administrative boundaries within an Active Directory forest
* Provides a means for organizing and managing network resources in a hierarchical manner


# Trust Relationship

A trust relationship in Active Directory is a method of connecting two distinct Active Directory domains or forests to allow users in one domain or forest to authenticate against resources in the other

## Trust Relationship Components

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Trust%20Relationship.png)

### Trusting Domain

The trusting domain is the domain that establishes the trust relationship with another domain

* Authenticates and grants access to its resources to the objects that are in the trusted domain

### Trusted Domain

The trusted domain is the domain that's trusted by another domain

* Users can authenticate and access resources in the trusting domain based on the established trust relationship

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Types of Trust Relationships

### One-Way Trust Relationship

A one-way trust relationship in Active Directory is a trust configuration where trust is established between two domains in one direction only

* Allows users in the trusting domain to access resources in in the trusted domain, but not vice-versa
* Ex: *If Domain A trusts Domain B, then Domain A is the trusting domain, and Domain B is the trusted domain*

### Two-Way Trust Relationship

A two-way trust relationship in Active Directory is a trust configuration where trust is established between two domains in both directions

* Allows users in both domains to authenticate and access resources in each other's domain
* Ex: *Domain A trusts Domain B and vice-versa*

### Transitive Trust Relationship

A transitive trust relationship is a trust configuration where trust relationships are extended beyond the directly connected domains

* Allows for indirect trust between domains in a multi-domain or multi-forest environment
* Ex: *If Domain A trusts Domain B, and Domain B trusts Domain C, then Domain A implicitly trusts Domain C*

### Shortcut Trust Relationship

A shortcut trust relationship in Active Directory is a trust configuration where trust is directly established between two domains within the same forest

* Provides a direct and efficient authentication path between the two domains
* Used between domains that belong to the same Active Directory forest
* Optimizes authentication traffic between two domains, bypassing the need to route authentication requests through the entire forest hierarchy
* The trust relationship is bidirectional, meaning that both domains trust each other for authentication purposes
* Improves authentication performance and reduces latency between the two domains

### External Trust Relationship

An external trust relationship in Active Directory is a trust configuration where trust is established between domains that reside in separate Active Directory forests

* Used when the trusting and trusted domains belong to different Active Directory forests
* The trust relationship is unidirectional, meaning that trust is established in one direction only (Administrators can configure them to be bidirectional if needed)
* Allows users in the trusting domain to authenticate and access resources in the trusted domain
* Users in the trusted domain don't automatically have access to resources in the trusting domain unless explicitly granted permissions

###  Forest Trust Relationship

A forest trust relationship in Active Directory is a trust configuration where trust is established between two separate Active Directory forests

* Enables users and resources in one forest to access resources in a completely different forest that has its own separate instance of Active Directory with its own domain structure, schema, and configuration
* The trust relationship is transitive, meaning that if Forest A trusts Forest B and Forest B trusts Forest C, then Forest A automatically trusts Forest C

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# AD Services

## AD DC

A Domain Controller (DC) is a server that serves as the central authority for authenticating and authorizing users and computers within a Windows domain network

* Authenticates users and computers when they attempt to log in to the domain
* Enforces security policies and permissions to determine what resources the authenticated users and computers are allowed to access within the domain
* Stores and hierarchically manages directory information (Ex: *User accounts*, *Group memberships*, *Computer accounts*, *OUs*, *etc.*)
* Replicates directory information with other Domain Controllers within the same domain to ensure consistency and fault tolerance (Allows changes made on one Domain Controller to be propagated to others, maintaining a consistent view of the directory services across the domain)
* Can host a copy of the global catalog, which contains a partial replica of all objects in the entire AD forest (The global catalog of a domain facilitates searching and locating objects across domains within the forest)
* Process Group Policy settings, which are used to define and enforce security and configuration settings for users and computers within the domain
* Establishes and maintains trust relationships with other domains and forests, allowing users in one domain to access resources in trusted domains
* Authenticates service requests within the same domain (Ex: *Requests for accessing shared resources, printers, or applications*, *etc.*)

