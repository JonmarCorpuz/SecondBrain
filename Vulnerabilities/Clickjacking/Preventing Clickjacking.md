# Preventing Clickjacking Techniques

* Add either the `X-Frame-Options: DENY` or `X-Frame-Option: SAMEORIGIN` to the HTTP response header
* Adding either the `Content-Security-Policy: frame-ancestors 'none'` or `Content-Security-Policy: frame-ancestors 'self' *.example.com` to the HTTP response header
* Set the `SameSite` flag on a cookie to either `Strict` or `Lax` to ensure that the cookie won't be sent in requests made within a third-party iframe
* Implement frame-busting, which is a technique that uses JavaScript code to check if the page is in an ifram and if it's framed by a trusted site
