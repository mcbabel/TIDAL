### Authorization Code + PKCE
* Used by the web player and the [Official TIDAL API](OfficialAPI) for user login
* Create a `code_verifier` (random 32 bytes, base64url without padding) and the `code_challenge` = base64url(sha256(code_verifier)) without padding
* Open the login url in a real browser or webview. The login page is bot protected, do not fill it programmatically.
* After login TIDAL redirects to `{redirect_uri}?code={code}`. [Exchange](auth-token#get-token-with-codeverifier) the code with an access_token and a refresh_token.
#### Example Request
##### Method
```GET``` (Browser)
##### Url
```https://login.tidal.com/authorize?response_type=code&client_id={client_id}&redirect_uri={redirect_uri}&scope={scope}&code_challenge={code_challenge}&code_challenge_method=S256```
##### Optional Url Parameter
```client_unique_key={client_unique_key}``` (random 64 bit hex value per installation)\
```state={state}```
#### Example Redirect
```{redirect_uri}?code={code}&state={state}```

#### Update 2026-11: Test status
The account owner logged in to the web player through `login.tidal.com`, which is this flow. The browser-based code exchange was not scripted (the login page is bot protected). The non-browser grants (device flow, client credentials, refresh, update_client) were run with the real app clients, see [auth-token](auth-token#update-2026-11-test-status-verified-with-real-app-clients). Client id/secret values are not reproduced here ([API Keys](Copyright)).

#### Update 2026-11: Android app (verified)
* The Android app uses `redirect_uri=https://tidal.com/android/login/auth`. Android opens the redirect in the app (App Link); in a browser the page shows "page not found". See [Android](Android).
