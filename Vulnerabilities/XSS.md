Cross-Site Scripting is an injection attack where malicious JavaScript gets injected into a web application with the intention of being executed by other users

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

* Relies on tricking a user into clicking a specially crafter link or submitting a malicious form, which then executes the malicious script in their browser

| Reflected XSS Method | Description |
| --- | --- |
| Parameters in the URL Query String | |
| URL File Path | |
| HTTP Headers | |

## Stored XSS

Stored XSS is when a malicious script that was injected by an attacker is permanently stored on the target web server (Ex: *Database*, *Message forum*, *Comment field*, *etc.*)

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/cc2566d297f7328d91bc8552f902210e.png)

* When other users view the affected content, the malicious script is served and executed in their browsers

| Stored XSS Method | Description |
| --- | --- |
| Comments | |
| User Profile Information | |
| Website Listings | |
| Forms | |

## DOM-Based XSS

DOM-Based XSS occurs when the client-side script of a web application manipulates the Document Object Model in an unsafe way based on user input

* The JavaScript execution happends directly and entirely on the client-side
* No new pages aren't loaded and no data is submitted to the back end
* The JavaScript code acts on input or user interaction

| DOM-Based XSS Method | Decription |
| --- | --- |
| Unsafe JavaScript Methods | (Ex: *eval()*) |

## Blind XSS

Blind XSS is when a threat actor injects malicious scripts into a web application without immediately seeing the results

* Useful when the injected script is stored and later executed in a different context or viewed by a subject that has access to a part of the application that the attacker can't directly see
* Similar to a Stored XSS

| Stored XSS Method | Decription |
| --- | --- |


