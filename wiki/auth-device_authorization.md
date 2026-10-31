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
