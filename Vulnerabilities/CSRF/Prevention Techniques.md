# CSRF Prevention Techniques

## CSRF Tokens

* Ensures the authenticity of requests
* Applications can embed these random and unpredictable strings in every form on their website and browsers will send this string along with every state-changing request (When the request reaches the server, the server can validate the token to make sure the request indeed originated from its website)
* Should be unique for each session and/or HTML form so attackers can't guess the token's value and embed it on their websites
* The server generates random CSRF tokens and embeds correct CSRF tokens in forms on the legitimate site
* If the value of `csrf_token` in the HTTP request is missing or incorrect, the server should see the request as fake and reject it

## SameSite

* Prevents browsers from sending cookies on cross-site form POST or AJAX requests, and within iframes and image tags
* Having the `SameSite=Strict` flag set will tell the client's browser to not send the cookie during cross-site requests
* Having the `SameSite=Lax` flag set will tell the client's browser to send a cookie only in requests that cause top-level navigation (Ex: *When users actively click a link and navigate to the site*, *etc.*) to ensure that users still have access to the resources on the website if the cross-site request was intentional 

## Double-Submit Cookie

* The state-changing request contains the same random token as both a cookie and a request parameter, and the server checks whether the two values are equal (If the values match, the request is seen as legitimate, otherwise then the application rejects it)
* It doesn't always matter whether or not the token themselves are valid, as long as the token in the cookies is the same as the token in the request parameter
