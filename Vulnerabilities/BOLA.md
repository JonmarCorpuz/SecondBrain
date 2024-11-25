Broken Object Level Authorization is a vulnerability that allows a system to incorrectly allow access to objects based on user inputs without properly checking if the user is authorized to access those objects

![](https://github.com/JonmarCorpuz/SecondBrain/blob/main/Assets/Whitespace.png)

# BOLA Mitigations

* Can be prevented by checking for valid access tokens or authorisation tokens in the header that the endpoint will check to see if the request is authorized
* The use of completely random values to prevent token predictions 
