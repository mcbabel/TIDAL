##### DRM-Free
Because of copyright infringing activities ([TIDAL-DL](https://github.com/yaronzz/Tidal-Media-Downloader)), I removed all client_ids and client_secrets.


##### Update 2026-11
The TIDAL **Android** app ships its OAuth client credentials in clear text in `assets/secrets.properties`: about two dozen `{variant}Id` / `{variant}ClientId` / `{variant}ClientSecret` triples (phone Default, HiRes, HiResV2, Clear, Dolby Atmos, Automotive, TV, FireTV, Bits, Facebook Portal, Stage), each client id 16 chars and secret 43 chars. These were used to verify the OAuth flows ([auth-token](auth-token), [Client Credentials](auth-client-credentials), [Device Authorization](auth-device_authorization)). The actual values are **not reproduced in this documentation**, following the policy above (they would enable copyright-infringing download tools). Register your own app at [developer.tidal.com](https://developer.tidal.com) for the [Official API](OfficialAPI).