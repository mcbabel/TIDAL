Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Search results for a query across tracks, albums, artists, and other content.

#### Resource `searchResults`
| Attribute | Type | Description |
|---|---|---|
| `didYouMean` (optional) | string | 'did you mean' prompt |
| `query` | string | The search query represented by this resource |
| `trackingId` | string | search request unique tracking number |

Relationships (`include=`): `albums`, `artists`, `playlists`, `topHits`, `tracks`, `videos`

### Get search results by query
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Searches for a query and returns a collection containing exactly one search results resource.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[query]` | query | yes | string | Search query (e.g. `hello`) |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, artists, playlists, topHits, tracks, videos |
| `includeLinkage` | query |  | string[]: albums, artists, playlists, topHits, tracks, videos | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get albums relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults/{id}/relationships/albums```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves albums relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search results identifier |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: albums |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults/{id}/relationships/artists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search results identifier |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: artists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get playlists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults/{id}/relationships/playlists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves playlists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search results identifier |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: playlists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: playlists.items |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get topHits relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults/{id}/relationships/topHits```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves topHits relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search results identifier |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: topHits |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: topHits |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get tracks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults/{id}/relationships/tracks```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves tracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search results identifier |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: tracks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: tracks |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get videos relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/searchResults/{id}/relationships/videos```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`, `search.read`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves videos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | An opaque search results identifier |
| `clientVersion` | query |  | string | Client version number |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `deviceType` | query |  | string: BROWSER, CAR, DESKTOP, PHONE, TABLET, TV | The type of device making the request |
| `explicitFilter` | query |  | string: INCLUDE, EXCLUDE | Explicit filter. Valid values: INCLUDE or EXCLUDE |
| `include` | query |  | string[] | Include related resources. Available relationships: videos |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: videos |
| `systemType` | query |  | string: ANDROID, DESKTOP, TESLA, IOS, WEB | The system type of the device making the request |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
