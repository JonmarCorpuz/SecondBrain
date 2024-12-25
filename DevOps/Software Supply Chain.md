# Software Supply Chain Overview

* Includes the people, processes, and tools that play a part in software development

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SLSA

Supply Chain Levels for Software Artifacts is a framework that outlines standards and controls that enhance the integrity of artifacts 

* Prioritizes placing trust in build platforms and code over the individuals that have access to them
* Doesn't assume a platform implements correct security measures
* Requires documentation that proves builds are securely configured
* Organizations can use SLSA standards and recommended technical controls to reinforce security throughout the supply chain

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SLSA Trust Boundaries

## Build Integrity

* Involves verifying the software uses the correct original dependencies (Ex: *Developers on a cloud security team should use unmodified source code and follow the work prescribed in their CI/CD pipeline*)

## Source Integrity

* Ensures that the source code actually reflects the developer's goals and intent
* Ensures that any code modifications are easily traced and monitored

## Dependencies

* Requires that any dependencies used in an artifact are examined using security checks

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SLSA Levels

* To achieve a higher level of security, SLSA splits the security levels into tracks
* Makes it easier to addess specific security concerns by allowing developers on a cloud security team to complete a track separate from the others
* Each level of the build track focuses on establishing provenance, which is a description of the processes and tools used to build an artifact

## Build L0

## Build L1

## Build L2

## Build L3

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# SLSA Technical Controls

## Version Control

## Vulnerability Scanning

## Build Verification

## Deployment Policies 

## Artifact Management
