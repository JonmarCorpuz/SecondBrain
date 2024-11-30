# Google Dorking Overview

* Can be a means to discovering valuable information (*Admin portals*, *Unlocked password files*, *Leaked authentication keys*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Google Search Engine Operators

## search

`search:<STRING>` tells Google what to search for

## site

`site:<WEBSITE>` tells Google to show you results from a certain site only

## inurl

`inurl:<URL>` tells Google to search for pages with a URL that match the search string

* Can be used to search for vulnerable pages on a particular website

## intitle

`intitle:<STRING>` tells Google to find specific strings in a page's title

* Allows you to find pages that contain a particular type of content

## link

`link:<LINK>` tells Google to search for web pages that contain links to a specific URL

* Allows you to find documentation about obscure technologies or vulnerabilities

## filetype

`filetype:<FILE_EXTENSION>` tells Google to search for pages with a specific file extension

* Can be used to locate files on a website that might be sensitive (*Log files*, *Password files*, *etc.*)

## *

The `*` wildcard tells Google to search for any character or series of characters within a search

## ""

Adding quotation marks (`" "`) around your search term tells Google to search for an websites that contain every single word within the quotation marks

## |

The Or operator (`|`) tells Google to search for one term or the other, or both at the same time

* Must be surrounded by spaces (Ex: *site:(site1 | site2) filetype:csv*)

## -

The `-` operator tells Google to exclude certain search results

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Google Dorking Queries

* Keep in mind that if you're sending a lot of search queries, Google will start requiring CAPTCHA challenges for visitors from your network before they can perform more searches

## General Information

Search for a target's subdomains
```Text
site:*.example.com
```

Search for potential text files that contain passwords
```Text
site:example.com ext:txt password
```

## AWS

Search for potential S3 AWS buckets
```Text
site:*.s3.amazonaws.com
```
```Text
site:s3.amazonaws.com <COMPANY NAME>
```

## GCP
