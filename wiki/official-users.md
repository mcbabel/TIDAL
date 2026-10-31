#### Example Request (verified 2026-11)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/users/me```
##### Header
```Authorization: Bearer {access_token}``` (PKCE, scope `user.read`)\
```Accept: application/vnd.api+json```
#### Example Response

``` yaml
{
  "data": {
    "id": "123456789",
    "type": "users",
    "attributes": {
      "username": "test@example.com",
      "country": "DE",
      "email": "test@example.com",
      "emailVerified": true,
      "developerAccessTier": "THIRD_PARTY"
    }
  },
  "links": {
    "self": "/users/me"
  }
}
```
#### Notes
* With a Client Credentials token: `403 {"errors":[{"code":"UNAUTHORIZED","detail":"Authenticated user is required"}]}`
* Fields you have no scope for are left out of the response instead of causing an error.
