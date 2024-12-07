# Clickjacking Overview

Clickjacking is an attack that tricks users into clicking a malicious button that has been made to look legitimate by using HTML page-overlay techniques to hide one web page within another (Ex: *Layering a Subscribe button over an invisible Transfer Funds buttong*)

* Usually involves a lot of user interaction on the victim's part
* Relies on HTML iframes, which allow developers to embed one web page within another by placing an `<iframe>` tag on the page and then specifying the URL to frame in the tag's `src` attribute
* iframes introduce the possibility of a clickjacking attack
* Two conditions need to be met for a clickjacking vulnerability to happen: The vulnerable page has to have functionality that executes a state-changing action on the user's behalf which causes changes to the user's account in some way and the vulnerable page has to allow itself to be framed by an iframe on another site

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)
