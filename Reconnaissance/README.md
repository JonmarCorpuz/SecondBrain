# Reconnaissance Techniques

## Google Dorking

## Certificate Parsing

* An SSL certificate's `Subject Alternative Name` field lets certificate owners specify additional hostnames that use the same certificate

## Subdomain Enumeration

## Service Enumeration

## Directory Enumeration

* Allows you to learn more about the structure and technology of an application (Ex: *A pathname that includes phpmyadmin usually means that the application is built with PHP*)

## Web Crawling

Web crawling is a process used to identify all pages on a website

* Allows users to potentially uncover many hidden endpoints in an application by identifying all the URLs embedded on the page and then visiting them

## Third-Party Hosting 

* Looking for a company's third party hosting footprint (*Google search*, *Github repositories*, *etc.*)
* Their resources on third-party hosting services can sometimes contain useful information (Ex: *Backups*, *Source code*, *Credentials*, *Logs*, *Hidden endpoints*, *etc.*)

## Github Recon

* Search an organization's GitHub repositories for sensitive data that has been accidentally committed, or information that could lead to the discovery of a vulnerability
* For each repository, pay attention to the Issues and Commit sections since they can be full of potential information leaks (*Unresolved bugs*, *Problematic code*, *Most recent code fixes*, *Most recent security patches*, *etc.*)
* Recent code changes that haven't stood the test of time are more likely to contain bugs
* Try to look for hardcoded secrets (*API keys*, *Encryption keys*, *Database passwords*, *etc.*)
* Pay attention to code that deals with user input (*HTTP request parameters*, *HTTP headers*, *HTTP request paths*, *Database entries*, *File reads*, *File uploads*, *etc.*) because they provide potential entry points for attackers to exploit the application's vulnerabilities
* Look for any configuration files that'll allow you to gather more information about your infrastructure
* Search for old endpoints and S3 bucket URLs that you can attack
* Pay attention to dependencies and imports being used and go through the versions list to see if they're outdated

## Fingerprinting

Fingerprinting is identifying the software brands and versions that a machine or an application uses

* Allows you to perform targeted attacks on the application 
* You can fingerprint an application by interacting with it directly (Ex: *Nmap scan using the -sV option*, *Check the HTTP headers in a HTTP response*, *View HTML source code for an embed signature within the source code*, *Check for technology-specific file extensions, filenames, folders, and directories*, *etc.*)
