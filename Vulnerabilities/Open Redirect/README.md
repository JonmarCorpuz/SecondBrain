# Open Redirect Overview

An open redirect attack happens when an attacker is able to manipulate the value of HTTP or URL parameters ro redirect a user offsite (The attacker tricks the user into visiting and external site by providing them with a URL from the legitimate site that redirects somewhere else

* An application may use some sort of redirect URL parameter appended to the URL to keep track of the user's original location (This helps determine where to redirect the user after login, ex: *https://example.com/login?redirect=https://example.com/dashboard*)
* Redirecting users automatically saves them time and improves their experience

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Open Redirect Techniques

## Referer-Based Open Redirect

* The referer is an HTTP request header that browsers automatically include (It tells the server where the request originated from)
* Referer headers are a common way of determining the user's original location since they contain the URL that linked to the current page (Meaning that some sites will redirect to the page's referer URL automatically after certain user actions)
