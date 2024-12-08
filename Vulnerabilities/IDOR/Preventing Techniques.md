# Preventing IDOR Techniques

* Check the user's identity and permissions before granting access to a resource (Ex: *Check if the user's session cookies correspond to the user_id whose messages the user is requesting*)
* The website can use a unique and unpredictable key or a hashed identifier to reference each user's resources
