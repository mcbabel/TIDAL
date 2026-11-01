Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A music video.

#### Resource `videos`
| Attribute | Type | Description |
|---|---|---|
| `availability` (optional) | string[] (STREAM, DJ, STEM) | Available usage for this video. Deprecated: use 'usageRules' instead. This field will be removed in a future version. **Deprecated.** |
| `copyright` (optional) | Copyright | Copyright information |
| `duration` | string | Duration (ISO 8601) |
| `explicit` | boolean | Explicit content |
| `externalLinks` (optional) | External_Link[] | Video links external to TIDAL API |
| `isrc` | string | International Standard Recording Code (ISRC) |
| `popularity` | number (double) | Popularity (0.0 - 1.0) |
| `releaseDate` (optional) | string (date) | Release date (ISO-8601) |
| `title` | string | Video title |
| `version` (optional) | string | Video version, complements title |

Relationships (`include=`): `albums`, `artists`, `credits`, `providers`, `replacement`, `similarVideos`, `suggestedVideos`, `thumbnailArt`, `usageRules`

### Get multiple videos
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple videos by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[id]` | query |  | string[] | List of video IDs (e.g. `75623239`) |
| `filter[isrc]` | query |  | string[] | List of ISRCs (e.g. `QMJMT1701237`) |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, artists, credits, providers, replacement, similarVideos, suggestedVideos, thumbnailArt, usageRules |
| `includeLinkage` | query |  | string[]: albums, artists, credits, providers, replacement, similarVideos, suggestedVideos, thumbnailArt, usageRules | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single video
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single video by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, artists, credits, providers, replacement, similarVideos, suggestedVideos, thumbnailArt, usageRules |
| `includeLinkage` | query |  | string[]: albums, artists, credits, providers, replacement, similarVideos, suggestedVideos, thumbnailArt, usageRules | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get albums relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/albums```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves albums relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albums |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/artists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: artists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get credits relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/credits```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves credits relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `include` | query |  | string[] | Include related resources. Available relationships: credits |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: credits.artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get providers relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/providers```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves providers relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: providers |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get replacement relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/replacement```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves replacement relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: replacement |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: replacement |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get similarVideos relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/similarVideos```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves similarVideos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: similarVideos |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: similarVideos |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get suggestedVideos relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/suggestedVideos```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves suggestedVideos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: suggestedVideos |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: suggestedVideos |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get thumbnailArt relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/thumbnailArt```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves thumbnailArt relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: thumbnailArt |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get usageRules relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/videos/{id}/relationships/usageRules```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves usageRules relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Video id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: usageRules |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
