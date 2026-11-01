#### Example Request
##### Method
```DELETE```
##### Url
```https://api.tidal.com/v1/users/{id}/clients/{clientId}/offline/playlists/{uuid}?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

```
204 No Content
````

#### Update 2026-11 (not executed)
Not tested: needs a client that is authorized for offline (mobile/desktop app with downloads). The web player has no offline mode, and the test account has no such client, so there is nothing to delete. See [Status of legacy endpoints](legacy-status).
