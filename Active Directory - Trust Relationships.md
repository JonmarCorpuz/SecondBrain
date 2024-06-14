

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
