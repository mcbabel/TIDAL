Cookie based single sign-on between tidal.com, account.tidal.com, offer.tidal.com and the web player (from web player code 2026-11, not live-tested).

### Get Tokens From Web Session (from web player code 2026-11, not live-tested)
* Returns `access_token`, `refresh_token`, `expires_in`, `user_id`, `scope` if the browser has a TIDAL login cookie. `204`/`401`/`403`: no session.
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/web-session/credentials```
##### Header
```Content-Type: application/json``` (with cookies, `credentials: include`)
##### Body
``` yaml
{
  "clientId": "{client_id}",
  "clientUniqueKey": "{client_unique_key}",
  "scope": "{scopes}"
}
```

### Log Out Web Session (from web player code 2026-11, not live-tested)
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/web-session/logout```
##### Header
(with cookies)

### Hydrate Session (from web player code 2026-11, not live-tested)
* Turns an access token into a tidal.com session cookie before redirecting to account/offer pages.
##### Method
```POST```
##### Url
```https://tidal.com/api/session/hydrate```
##### Header
```Content-Type: application/json``` (with cookies)
##### Body
``` yaml
{
  "accessToken": "{access_token}"
}
```
