Cookie based single sign-on between tidal.com, account.tidal.com, offer.tidal.com and the web player (from web player code 2026-11, not executed).

### Get Tokens From Web Session (from web player code 2026-11, not executed)
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

### Log Out Web Session (from web player code 2026-11, not executed)
##### Method
```POST```
##### Url
```https://auth.tidal.com/v1/web-session/logout```
##### Header
(with cookies)

### Hydrate Session (from web player code 2026-11, not executed)
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

#### Update 2026-11: Test status
* **web-session/credentials**: not observed and not called. The web player only calls it when it has no stored token (first visit with a login cookie). The test browser already had a token, and calling it manually means logging in with the session cookie.
* **web-session/logout**: not called. It would log the account out of the browser.
* **session/hydrate**: not observed. Opening the account pages from the web player did not use it (the account page used the existing cookie). It is used in the sign-up/upgrade redirect to offer.tidal.com.
