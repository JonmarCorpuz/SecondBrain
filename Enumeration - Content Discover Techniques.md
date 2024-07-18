Content discovery is the process of identifying and mapping out all the content and resources available on a web application (Ex: *Hidden directories and files*, *Backup files*, *Configuration files*, *Sensitive data*, *Development and test environments*, *Administration panels*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Manual Content Discovery 

| Manual Content Discovery Method | Description |
| --- | --- |
| Robots.txt | A document that tells search engines which pages they're allowed and not allowed to show on their search engine results or ban specific search engines from crawling the website altogether (Ex: *Administration portals*, *Files meant for the website's customers*, *etc.*) |
| Favicon | Sometimes when frameworks are used to build a website, a favicon that's part of the installation gets leftover, and if the website developer doesn't replace it with a custom one, it can give us a clue on what framework is in use |
| Sitemap.xml | Sitemap.xml gives a list of every fiile the website owner wishes to be listed on a search engine, which can sometimes list old webpages that the current sire no longer uses but are still working behind the scenes
| HTTP headers | The HTTP headers that are returned by a server can sometimes contain useful information (Ex: *The programming or scripting language that's in use*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Automated Content Discovery 

| Automated Content Discovery Tool | Description |
| --- | --- | 
| ffuf |  |
| gobuster |  |
| dirb |  |

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# OSINT

| OSINT Technique | Description |
| --- | --- |
| Google Dorking | A technique that uses advanced search operators in GOogle Search to find information that's not readily available through regular search queries |
| Wappalyzer | An online tool and browser extensions that helps identify what technologies a website uses (Ex: *Frameworks*, *Content Management Systems*, *Payment processors*, *etc.*) |
| Wayback Machine | A historical archive of websites, which you can go and search a domain name and it'll show you all the times the service scraped the web page and saved the contents |
| Github | Can be used to search for repositories that belongs to your target |
| S3 Buckets | Sometimes access permissions are incorrectly set and indavertently allow access to files that should be available to the public | |
