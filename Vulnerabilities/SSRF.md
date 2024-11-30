Server-Side Request Forgery is a vulnerability that allows a malicious user to cause the webserver to make an additional or edited HTTP request to a resource

* Based on JavaScript

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

| SSRF Method | Description | Example |
| --- | --- | --- |
| URL Parameter Bar | | *http://example.com/form?server=http://example.com/store* |
| HTML Field Form | | *<input type="hidden" name="example" value="http://example.com/store">* |
| Alternate References | Bypasses deny lists | *Alternative localhost references such as 127.1* |
| Fake Subdomain | Bypasses allow lists | *subdomain.example.com* |
| Open Redirect | | *http://website.com/link?url=http://redirected-url.com* |

# Types of SSRF

Data is returned to the attacker's screen

## Regular SSRF

No data is returned to the attacker's screen

## Blind SSRF