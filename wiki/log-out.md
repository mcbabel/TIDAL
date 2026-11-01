#### Example Request
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/logout```

##### Header
```authorization: Bearer {access_token}```
#### Example Response

```204 No Content```

#### Update 2026-11 (not executed)
Not tested on purpose: the call invalidates the session of the access token. In the test the token belonged to the user's own logged-in browser session, so the call would log the user out. The web player itself logs out with [web-session/logout](web-session) plus this endpoint.
