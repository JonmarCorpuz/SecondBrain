# Clickjacking Overview

Clickjacking is an attack that tricks users into clicking a malicious button that has been made to look legitimate by using HTML page-overlay techniques to hide one web page within another (Ex: *Layering a Subscribe button over an invisible Transfer Funds buttong*)

* Usually involves a lot of user interaction on the victim's part
* Relies on HTML iframes, which allow developers to embed one web page within another by placing an `<iframe>` tag on the page and then specifying the URL to frame in the tag's `src` attribute
* iframes introduce the possibility of a clickjacking attack
* Two conditions need to be met for a clickjacking vulnerability to happen: The vulnerable page has to have functionality that executes a state-changing action on the user's behalf which causes changes to the user's account in some way and the vulnerable page has to allow itself to be framed by an iframe on another site
* Only allows the attacker to forge only a user's clicks and not their keyboard actions

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Hunting for Clickjacking

## Step 1: Check for State-Changing Actions

You should look for pages that allow users to make changes to their accounts (*Changing account details*, *Changing account settings*, *etc.*)

* Clickjacking vulnerabilities are valuable only when the target page contains state-changing actions (*Change password*, *Transfer balance*, *Unlink external accounts*, *etc.*)
* Keep a note of the URL locations for the pages that require only mouse clicks to execute for further testing

## Step 2: Check the Response Headers

Go through each of the state-changing functionailities you've found and revisit the pages that contain them using a proxy to intercept the HTTP response to see if the page is being served with the `X-Frame-Options` or `Content-Security-Policy` header (If the page is served without any of these headers then it may be vulnerable to clickjacking)

* You should also check if the target application uses `SameSite` cookies if the state-changing action requires users to be logged in when it's executed (You won't be able to exploit clickjacking on the site's feature if it does since this means that it would require a user to be authenticated)

## Step 3: Confirm the Vulnerability

Confirm the vulnerability by executing a clickjacking attack on your test account

* Craft an HTML page that frames the target page and load that page in a browser to see if the page has been framed
* Craft a way to deliver your payload to end users
