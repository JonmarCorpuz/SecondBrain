# VM Instance Components

| VM Instance Component | Description | 
| --- | --- |
| Internal IP Address | Internal to a Google Cloud network |
| External IP Address | Internet addressable |

## Internal IP Address

* All VM instances are assigned at least one internal IP address
* Still assigned to a VM intance even after it's stopped

## External IP Address

* Lost when a VM instance is stopped unless it was assigned a static IP address (A static address should be in the same region as your VM instance and should be released when you're no longer using it since you're billed for a static IP address even when you're not using it)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# VM Instance Templates

* Can't be modified once it's created (To make modifications, simply copy the existing template and modify it)
* A image family can be specified (The latest non-deprecated version of the family is used by default)
* Can be used to create VM instances in multiple different regions and zones
