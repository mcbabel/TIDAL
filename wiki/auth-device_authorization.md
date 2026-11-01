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

#### Update 2026-11: Test status
Not executed. Running a login flow needs the `client_id` (and for some flows the `client_secret`) of an app. The client ids of TIDAL's own apps are intentionally not used or published in this documentation ([API Keys](Copyright)), and no own developer app was registered for the test. The endpoint itself was verified to exist (`GET` answers `405 Method Not Allowed`).
