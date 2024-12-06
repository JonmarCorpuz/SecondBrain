# Bypassing Open-Redirect Protection

* Different browsers can handle the same URL differently (`https://user:password:8080/example.com@attacker.com`, *etc.*)
* Sometimes validators don't account for all the edge cases that can cause the browser to behave unexpectedle
* URL components: `scheme://userinfo@hostname:port/path?query#fragment`

## Using Browser Autocorrect

You can use browser autocorrect features to construct alternative URLs that redirect offsite

* Some modern browsers often autocorrect URLs that don't have the correct components in order to correct mangled URLs cause by user typos (Ex: *https:example.com/page, https;example.com/page, https:\/\/example.com/page, https;\/\/example.com/page, https:\\example.com\page, and https://example.com\page will all point to https://example.com/page*)
* Helps you bypass URL validation based on a blocklist

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

## Exploiting Flawed Validator Logic

You can bypass the open-redirect validator by exploiting loopholes in the validator's logic

* Some URL validators check if the redirect URL starts with, contains, or ends with the site's domain name, which you can bypass by creating a subdomain or directory with the target's domain name

```Text
https://example.com/login?redirect=http://example.com.attacker.com
https://example.com/login?redirect=http://attacker.com/example.com
https://example.com/login?redirect=http://example.com.attacker.com/example.com
https://example.com/login?redirect=https://exmaple.com@attacker.com/example.com
```

## Using Data URLs

You can manipulate the scheme portion of the URL to fool the validator

* You can use the `data:` scheme to construct a base64-encoded redirect URL that evades the validator

```Text
https://example.com/login?redirect=data:text/html;base64,<BASE64_ENCODED_STRING>
```

## Exploiting URL Decoding

URL encoding converts a character into a percentage sign, followed by two hex digits (Ex: *%2f is the URL-encoded version of /*)

* When validators validate URLs or when browsers redirect users, they have to first find out what is contained in the URL by decoding any characters that are URL encoded (If there's any inconsistency between how the validator and browsers decode URLs, you could exploit that to your advantage)

Double-URL-encoding
```Text

```

Triple-URL-encoding
```Text

```
