# Bypassing Clickjacking Protection Techniques

If the application fails to implement complete clickjacking protections, you might be able to bypass the mitigations

* Clickjacking isn't possible when the application's implements the proper protections (Ex: *If a browser displays an `X-Frame-Options` protected page, chances are you can't exploit clickjacking on the page*, *etc.*)
 
## Double iframe Trick

This trick works by framing your malicious page within a page in the victim's domain
