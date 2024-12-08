# Bypassing CSRF Techniques

* If the CSRF protection is incomplete or faulty, then you might still be able to achieve a CSRF attack with a few modifications to your payload

## Clickjacking

If the endpoint uses CSRF tokens but the page itself is vulnerable to clickjacking, then you can exploit clickjacking to achieve the same results as CSRF

## Change the Request Method

Sometimes websites will accept multiple request methods for the same endpoint, but protection might noe be in place for each of those methods

* Changing the request method might allow you to get the action executed without encountering CSRF protection (Ex: *Using GET instead of POST*, *etc.*)

## Exploiting Common Application Logic Mistake

* Deleting the token parameter or sending a blank token often works because of a common application logic mistake (Applications sometimes check the validity of the CSRF token only if the token exists or if the token parameter is not blank)
* You can try to submit the request with another session's CSRF token because some applications might check only whether the token is valid, without confirming that it belongs to the current user
