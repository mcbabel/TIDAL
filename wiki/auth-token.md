### Get Token From DeviceCode
* Generate a DeviceCode
* Poll the auth_server every 2 seconds to check if the DeviceCode is authorized.
* If the DeviceCode is authorized within 300s / 5m a access_token and a refresh_token will be generated. The access_token lasts 604800s / 7 Days.
#### Example Request
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/token```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```device_code: {device_code}```\
```grant_type: urn:ietf:params:oauth:grant-type:device_code```\
```scope: r_usr+w_usr+w_sub```
##### HTTP Basic Authorization
```{client_id} : {client_secret}```

#### Example Response (Pending)
``` yaml
{
  "status": 400,
  "error": "authorization_pending",
  "sub_status": 1002,
  "error_description": "Device Authorization [DeviceAuthorization(id=xxxxxxx, userCode={user_code}, deviceCode={device_code}, clientToken={client_id}, userId=0, scopes=r_usr+w_usr+w_sub, created=Fri Oct 13 19:46:12 UTC 2020, validUntil=Fri Oct 13 19:51:52 UTC 2020, authorized=null, used=null, lastCheck=Fri Oct 13 19:48:35 UTC 2020)] is not authorized yet"
}
```
#### Example Response (Successful)

```yaml
{
  "access_token": {access_token},
  "refresh_token": {refresh_token},
  "token_type": "Bearer",
  "expires_in": 604800,
  "user": {
    "userId": 012345678,
    "email": null,
    "countryCode": "DE",
    "fullName": null,
    "firstName": null,
    "lastName": null,
    "nickname": null,
    "username": "test@example.com",
    "address": null,
    "city": null,
    "postalcode": null,
    "usState": null,
    "phoneNumber": null,
    "birthday": null,
    "gender": null,
    "imageId": null,
    "channelId": 0123,
    "parentId": 0,
    "acceptedEULA": true,
    "created": 0000000000000,
    "updated": 0000000000000,
    "facebookUid": 0,
    "appleUid": null,
    "newUser": false
  }
}
```
### Get Token From RefreshToken
* If your AccessToken has expired use the RefreshToken to get a new AccessToken
* Update 2026-11: The response can contain a new `refresh_token` (refresh token rotation). Always store it, otherwise the user is logged out after a few days.
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/token```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```refresh_token: {refresh_token}```\
```grant_type: refresh_token```\
```scope: r_usr+w_usr+w_sub```
##### HTTP Basic Authorization
```{client_id} : {client_secret}```
#### Example Response
```yaml
{
  "access_token": {access_token},
  "token_type": "Bearer",
  "expires_in": 604800,
  "user": {
    "userId": 012345678,
    "email": null,
    "countryCode": "DE",
    "fullName": null,
    "firstName": null,
    "lastName": null,
    "nickname": null,
    "username": "test@example.com",
    "address": null,
    "city": null,
    "postalcode": null,
    "usState": null,
    "phoneNumber": null,
    "birthday": null,
    "gender": null,
    "imageId": null,
    "channelId": 0123,
    "parentId": 0,
    "acceptedEULA": true,
    "created": 0000000000000,
    "updated": 0000000000000,
    "facebookUid": 0,
    "appleUid": null,
    "newUser": false
  }
}
```
### Get Token With CodeVerifier
* Use the Response Code from the web-based authorization flow
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/token```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```code: {code}```\
```redirect_uri: {redirect_uri}```\
```code_verifier: {code_verifier}```\
```client_unique_key: {client_unique_key}``` (optional)\
```grant_type: authorization_code```\
```scope: r_usr+w_usr+w_sub```
##### HTTP Basic Authorization
```{client_id} : {client_secret}`
#### Example Response

```yaml
{
  "access_token": {access_token},
  "refresh_token": {refresh_token},
  "token_type": "Bearer",
  "expires_in": 604800,
  "user": {
    "userId": 012345678,
    "email": null,
    "countryCode": "DE",
    "fullName": null,
    "firstName": null,
    "lastName": null,
    "nickname": null,
    "username": "test@example.com",
    "address": null,
    "city": null,
    "postalcode": null,
    "usState": null,
    "phoneNumber": null,
    "birthday": null,
    "gender": null,
    "imageId": null,
    "channelId": 0123,
    "parentId": 0,
    "acceptedEULA": true,
    "created": 0000000000000,
    "updated": 0000000000000,
    "facebookUid": 0,
    "appleUid": null,
    "newUser": false
  }
}
```
### Exchange User-AuthenticationToken With Token
#### Example Request
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/token```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```user_auth_token: {user_auth_token}```\
```client_version: {client_version}``` (optional)\
```client_unique_key: {client_unique_key}``` (optional)\
```grant_type: user_auth_token```\
```scope: r_usr+w_usr+w_sub```
##### HTTP Basic Authorization
```{client_id} : {client_secret}```

### Update 2026-11
* Current token responses additionally contain `scope`, `clientName` and `user_id` next to `access_token`, `refresh_token`, `token_type`, `expires_in` and `user`.
* Clients without HTTP Basic authorization can send ```client_secret: {client_secret}``` as Url-Encoded POST Parameter instead.
* `expires_in` differs between clients. Use the returned value instead of assuming 7 days.

### Get Token With ClientCredentials
* Token without a user (see [Client Credentials](auth-client-credentials))
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

### Update Client
* Moves an existing session to a new client_id / client_secret without a new login (used by the official TIDAL SDK)
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/token```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```client_secret: {client_secret}```\
```refresh_token: {refresh_token}```\
```grant_type: update_client```\
```scope: r_usr+w_usr+w_sub```

#### Update 2026-11: Test status
Not executed. Running a login flow needs the `client_id` (and for some flows the `client_secret`) of an app. The client ids of TIDAL's own apps are intentionally not used or published in this documentation ([API Keys](Copyright)), and no own developer app was registered for the test. The token responses are taken from the official TIDAL SDK (`tidal-sdk-web`, auth module) and python-tidal.
