# Bypassing IDOR Protection Techniques

## Change the Request Method

Applications often enable mutliple request methods on the same endpoint but fail to implement the same access control for each method

## Change the Requested File Type

Switching the file type of the requested file sometimes leads the server to process the authorization differently (Ex: *Applications commonly store information in JSON so try adding the .json extension to the end of the requested URL and see what happends*)
