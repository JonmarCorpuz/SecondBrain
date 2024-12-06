# Bypassing Open-Redirect Protection

* Different browsers can handle the same URL differently (`https://user:password:8080/example.com@attacker.com`, *etc.*)
* Sometimes validators don't account for all the edge cases that can cause the browser to behave unexpectedle

## Using Browser Autocorrect

You can use browser autocorrect features to construct alternative URLs that redirect offsite

* Some modern browsers often autocorrect URLs that don't have the correct components in order to correct mangled URLs cause by user typos (Ex: *https:example.com/page, https;example.com/page, https:\/\/example.com/page, https;\/\/example.com/page, https:\\example.com\page, and https://example.com\page will all point to https://example.com/page*)
* Helps you bypass URL validation based on a blocklist

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Exploiting Flawed Validator Logic

You can bypass the open-redirect validator by exploiting loopholes in the validator's logic

* Some URL validators check if the redirect URL starts with, contains, or ends with the site's domain name, which you can bypass by creating a subdomain or directory with the target's domain name (*https://example.com/login?redirect=http://example.com.attacker.com*, *https://example.com/login?redirect=http://attacker.com/example.com*, *etc.*)
