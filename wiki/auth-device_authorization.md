#### Example Request
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/oauth2/device_authorization```
##### Url-Encoded POST Parameter
```client_id: {client_id}```\
```scope: r_usr+w_usr+w_sub```
#### Example Response

``` yaml
{
  "deviceCode": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx",
  "userCode": "AFIDU",
  "verificationUri": "link.tidal.com",
  "verificationUriComplete": "link.tidal.com/AFIDU",
  "expiresIn": 300,
  "interval": 2
}
```

##### Optional Url-Encoded POST Parameter (Update 2026-11)
```client_secret: {client_secret}``` (only for clients that have one)\
```app_approval: true``` (the user approves the code inside a logged-in TIDAL app instead of on link.tidal.com; `verificationUriComplete` then looks like `https://tidal.com/approve/{code}`)

`GET` on this endpoint answers `405 Method Not Allowed` (verified 2026-11).

#### Update 2026-11: Test status (verified with real app clients)
The TIDAL Android app ships its OAuth client credentials in `assets/secrets.properties` (see [Android](Android)). With those, the full flow was run on 2026-11-01:
* **Device flow needs a limited-input client.** The phone client answers `400 {"error":"invalid_request","error_description":"Client is not a Limited Input Device client"}`. The TV and FireTV clients work and return the response above.
* The returned `userCode` was approved on `link.tidal.com`, then the [token endpoint](auth-token#get-token-from-devicecode) returned a real `access_token` + `refresh_token` (scope `r_usr w_usr w_sub`). This registers a client/device on the account; it was logged out again afterwards.
* The actual client ids and secrets are intentionally not reproduced here, see [API Keys](Copyright).
