Since 2024 TIDAL offers an official, public API. It is documented by TIDAL itself, versioned, and has a deprecation policy (deprecated functionality keeps working for at least six months).

* Base url: ```https://openapi.tidal.com/v2```
* Reference: https://tidal-music.github.io/tidal-api-reference/ (OpenAPI spec: `tidal-api-oas.json`, version `1.10.218` on 2026-11-01)
* Developer portal (register your app, get client_id / client_secret): https://developer.tidal.com
* Official SDKs: https://github.com/tidal-music (`tidal-sdk-web`, `tidal-sdk-android`, `tidal-sdk-ios`)
* [List of all Official API Endpoints](official-endpoints) (all 438 operations, each resource with a full reference page)
* [Migration Guide](Migration) (private API → official API)

##### Authentication
* [Client Credentials](auth-client-credentials): catalog without user
* [Authorization Code + PKCE](auth-pkce): user context (scopes: `user.read`, `collection.read`, `collection.write`, `playlists.read`, `playlists.write`, `search.read`, `search.write`, `recommendations.read`, `entitlements.read`, `playback`)
* Header: ```Authorization: Bearer {access_token}```

##### Access Tiers
Every endpoint has a required access tier: `THIRD_PARTY` (your app), `PARTNER`, `INTERNAL` (TIDAL's own apps). Of 438 operations in the spec, 101 are open to third-party apps. TIDAL's own web player uses the same API with internal access.

##### Format: JSON:API
* Content type: ```application/vnd.api+json``` (Accept and Content-Type)
* Resources: `{"id": "...", "type": "tracks", "attributes": {...}, "relationships": {...}}`. Ids are strings.
* `include=albums,artists` adds related resources to `included`. Nested: `include=artists.profileArt`. Max depth 3, max 10 resources.
* Relationships are only returned when requested (`include`).
* `me` can be used as user id: `/users/me`, `/userCollectionTracks/me`, `filter[owners.id]=me`
* Filtering: `filter[id]=1,2,3`, `filter[isrc]=...`, `filter[barcodeId]=...`
* Sorting: `sort=-addedAt` (descending), `sort=title`
* Pagination is cursor based: follow `links.next` (`page[cursor]=...`) until it is missing. No offset.
* Durations are ISO 8601 (`PT2M4S`), popularity is `0.0` - `1.0`.
* Mutations accept an `Idempotency-Key` header.
* Errors: ```{"errors":[{"code":"UNAUTHORIZED","detail":"..."}]}```

##### Example Request (verified 2026-11)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/38519997?countryCode=DE&include=albums,artists```
##### Header
```Authorization: Bearer {access_token}```\
```Accept: application/vnd.api+json```

See [Get Track (Official API)](official-track) for the response.
