# Open Redirect Overview

An open redirect attack happens when an attacker is able to manipulate the value of HTTP or URL parameters ro redirect a user offsite (The attacker tricks the user into visiting and external site by providing them with a URL from the legitimate site that redirects somewhere else

* An application may use some sort of redirect URL parameter appended to the URL to keep track of the user's original location (This helps determine where to redirect the user after login, ex: *https://example.com/login?redirect=https://example.com/dashboard*)
* Redirecting users automatically saves them time and improves their experience

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Hunting for Open Redirects

## Step 1: Look for Redirect Parameters

Start searching for the parameters used in redirects 

* Not all redirect parameters have straightforward names
* Take note of pages that don't contain redirect parameters in their URLs but still automatically redirect their users (*300 HTTP Response Codes*, *etc.*)

```Text
https://example.com/login?redirect=https://example.com/page
https://example.com/login?redir=https://example.com/page
https://example.com/login?next=https://example.com/page
https://example.com/login?next=/page
https://example.com/login?next=page
```

## Step 2: Use Google Dork to Find Additional Redirect Parameters

```Text
inurl:%3Dhttp site:example.com
inurl:%3D%2F site:example.com
inurl:redirect site:example.com
inurl:redir site:example.com
inurl:redirecturi site:example.com
inurl:redirect_uri site:example.com
inurl:redirecturl site:example.com
inurl:redirect_url site:example.com
inurl:return site:example.com
inurl:returnurl site:example.com
inurl:relaystate site:example.com
inurl:forward site:example.com
inurl:forwardurl site:example.com
inurl:forward_url site:example.com
inurl:url site:example.com
inurl:uri site:example.com
inurl:dest site:example.com
inurl:destination site:example.com
inurl:next site:example.com
```

## Step 3: Test for Parameter-Based Open Redirects

Pay attention to the functionality of each redirect parameter you've found and test each one for an open redirect 

* Insert a random hostname or a hostname you own into the redirect parameters then see if it automatically redirects you to the specified site
* Some sites will redirect to the destination site immediately after you visit the URL, others will redirect after a user action (*Registration*, *Login*, *Logout*, *etc.*)

## Step 4: Test for Referer-Based Open Redirects

Set up a page on a domain you own and host this HTML page
```HTML
<html>
  <a href="https://example.com/login">Click on this link</a>
</html>
```
