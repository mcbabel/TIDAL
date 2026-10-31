TIDAL uses OAuth2 for authorization. After authorization (Email or 3rd-Party) the response code is then exchanged with the accessToken (authorization: Bearer xxx in Header). The accessToken is only valid for 7 Days and has to be updated.

TIDAL has also implemented a DeviceFlow for devices with limited input (like TVs or NetworkStreamer) and applications that are not web-based (reCaptcha v3 in the webflow). Here the device requests a 5 character Authcode (userCode) and a DeviceCode. The user then links the AuthCode to his account and the DeviceCode can then be exchanged for an accessToken.

##### DeviceFlow

1. [Generate](https://github.com/openTIDAL/docTIDAL/wiki/auth-device_authorization) a DeviceCode and UserCode
2. Wait for the user to authenticate via link.tidal.com
3. [Exchange](https://github.com/openTIDAL/docTIDAL/wiki/auth-token) the DeviceCode with an access_token and a refresh_token

Authorization across the TIDAL API:\
Header: \
```authorization: Bearer {access_token}```

##### WebFlow
TIDALs Web Flow is reCaptcha v3 secured. Implementing reCaptcha v3 outside the web-browser is nearly impossible.\
Update 2026-11: Use the [Authorization Code + PKCE flow](auth-pkce) and let the user log in in a real browser. Your app only receives the redirect with the code.

##### Legacy Username&Password (Deprecated)
1. [Login](https://github.com/openTIDAL/docTIDAL/wiki/auth-username-password)
2. (Optional oAuth2 Migration) [Get the user_auth_token](https://github.com/openTIDAL/docTIDAL/wiki/loginToken) (You can used the previously received sessionId for authorization) and [exchange](https://github.com/openTIDAL/docTIDAL/wiki/auth-token#exchange-user-authenticationtoken-with-token) it with an access_token and refresh_token **(Use a MQA-Enabled client_id to enable MQA)**

Authorization across the TIDAL API with sessionId:\
Url Parameter: \
```sessionId={sessionId}```

Authorization across the TIDAL API after Migration:\
Header: \
```authorization: Bearer {access_token}```


##### Update 2026-11

###### Authorization Code + PKCE
See [Authorization Code + PKCE](auth-pkce). Used by the web player and by the [Official TIDAL API](OfficialAPI).

###### Client Credentials
Token without a user, see [Client Credentials](auth-client-credentials). Used by the [Official TIDAL API](OfficialAPI) and by the web player for logged-out visitors.

###### Anonymous catalog access
Most catalog GET endpoints (tracks, albums, artists, playlists, search, pages) work without a user with the header ```x-tidal-token: {client_id}```. Endpoints that need a user answer `401` with `subStatus 1005` "Missing auth parameter" (verified 2026-11).

###### Refresh Token Rotation
A [refresh](auth-token#get-token-from-refreshtoken) can return a new `refresh_token`. Always store it, otherwise the user is logged out after a few days. Refresh shortly before `expires_in` runs out and never run two refreshes with the same refresh token in parallel.

###### Scopes
* Private API: `r_usr`, `w_usr`, `w_sub`
* Official API: `user.read`, `collection.read`, `collection.write`, `playlists.read`, `playlists.write`, `search.read`, `search.write`, `recommendations.read`, `entitlements.read`, `playback`

###### After login
[Get Session](sessions) returns `userId` and `countryCode` of the current token.
