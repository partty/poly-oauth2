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


### beforeAuthorize
This event fires befor the request to be sent. It's a way to change the request befor sending it to the server.

### authorizeSuccess
This event fires on successful authorization. Use this for notifying the user that the authentication is successful

### authorizeError
This event is fired on errorous authentication. If the server returns a status code 4xx on wrong username or password (as it should) this event is fired when the password is wrong, but it also fired on 404 or other network or origin problems. Make sure you handle all of them apropriatly.

### authorizeComplete
This event is fired, no mather if there is an error or success. Use this to hide any spiners an loading screens


### refreshSuccess
This event is fired when the refresh ave been successful

### refreshFail
This event is fired on any error with the refresh request. Analogus with the authorize, this even will fire for any kind of status different from 200.

### refreshComplete
This is fired after every refresh request, no mather if it is a success or an error


### tokenChange
This event is fired everytime the access token is changed. In this sense the event is fired after successful authorization and after every successful refresh.
Use this event to handle access token changes. The simpler way to handle token changes is to use the accessToken property, wich is aways up to date. 



