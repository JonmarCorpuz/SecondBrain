# Open Redirect Prevention Techniques

* The server needs to make sure it doesn't redirect users to malicious locations
* Implement URL validators to ensure that the user-provide redirect URL points to a legitimate location (The validators use either a blocklist or an allowlist)
* A validator using a blocklist will check whether the redirect URL contains certain indicators of a malicious redirect and then block those requests accordingly
* A validator using an allowlist will check the hostname portion of the URL to make sure that it matches a predetermined list of allowed hosts (If the hostname portion of the URL matches an allowed hostname, the redirect goes through)
