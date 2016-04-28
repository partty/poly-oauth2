# poly-oauth2
Polymer based custom elemet that is a oauth2 client. 

This element is aimed to close the gap in comunicating with oauth2 server. It is invisible element that you control via javascript API. 
It has properties, methods and events, that make it strate forward to authenticate on oauth server, and then refresh the authentication automaticaly or manualy. The 'tockenChanged' event will help you stay in the loop, if you use autoRefresh.

## Properties
All the properties can be set using HTML properties to the element or by using the javascript API

### clientId (required) String
This property is required by oAuth2 and it is sent unchanged

### grantType (required) String
This property is required by oAuth2 and it is sent unchanged

## serverUrl (required) String
This is the url to your oAuth2 server. It must accepth "content type = application/json"

### username (required) String
This is the user name that is sent to the server. It's best if this property is set via the javascript API

### password (required) String
This is the user password is sent to the server. It's best if this property is set via the javascript API

### accessToken (readonly) String
This property holds the access token value. 

### refreshToken (readonly) String
This property holds the refresh token value. 

### tokenType (readonly) String
What kind of token the server returned.

### expiresIn (readonly) String
For how long this token is valid. This is the value reterned from the server.

### expiresAt (readonly) String
The date object for the moment of expiration of the token. This is calculatet when the token is received, so it can be wrong by second or two.

### scope (readonly) String
The authorisations scope, returned from the server.

### authorised (readonly) Bolean
This i a bolean flag that is true if at the moment the element is authorised. It is false if the 'authorize' method haven't been activated or if it returned an error. It's false also when the refresh have been unsuccessoful.


## Methods

### authorize ([username, password]) 
Asyncronusly sends an authorization request to the oAuth2 server. 

### refresh ()
Asyncronusly performs a refresh request to the oAuth2 server.


## Events

### refreshComplete
### refreshComplete

### refreshComplete

### refreshComplete

### refreshSuccess

### tokenChange



