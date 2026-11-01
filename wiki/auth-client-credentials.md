### Client Credentials
* Token without a user. Enough for all catalog endpoints of the [Official TIDAL API](OfficialAPI).
* No refresh_token. Request a new token when it expires.
#### Example Request
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/token```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```client_secret: {client_secret}```\
```grant_type: client_credentials```
#### Example Response
```yaml
{
  "scope": "",
  "token_type": "Bearer",
  "access_token": {access_token},
  "expires_in": {seconds}
}
```
#### Notes
* Endpoints that need a user answer `403 {"errors":[{"code":"UNAUTHORIZED","detail":"Authenticated user is required"}]}` (verified 2026-11).
* The web player uses a client credentials token for logged-out visitors.

#### Update 2026-11: Test status (verified)
Run on 2026-11-01 with the OAuth clients from the Android app's `assets/secrets.properties`:
``` yaml
{
  "scope": "",
  "token_type": "Bearer",
  "access_token": "…",
  "clientName": "TIDAL_Android_2.x.x",
  "expires_in": 14400
}
```
* Every app client variant (phone, HiRes, TV, …) returns a token; `clientName` tells which.
* The token has no user. It works for anonymous [Official API](OfficialAPI) catalog requests (`GET /tracks/{id}`, `/searchResults`, `/trackManifests/{id}` preview); user endpoints answer `403`.
* The client id/secret values are not reproduced here ([API Keys](Copyright)).
