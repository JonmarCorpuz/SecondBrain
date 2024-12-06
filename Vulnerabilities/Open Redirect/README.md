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

