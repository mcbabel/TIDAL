### Get User Auth-Token
* You can exchange the user_auth_token with an access_token and a refresh_token
* Available after login
* Use the sessionId={sessionId} Url Parameter for session based authorization
#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/loginToken?countryCode={country}```
##### Header
```authorization: Bearer {access_token}``` (Only if no sessionId Parameter is set)
#### Example Response
```yaml
{
  "authenticationToken": "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
}
```