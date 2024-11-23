# Secrets Overview

* Allows us to decouple and inject sensitive data into Pods
* Can be used to store and inject sensitive data into containers
* Help up not have to include sensitive information in application code
* The data is stored in base64-encoded and unencrypted by default
* Secrets can be passed either as environment variables or as files via volume mounts
