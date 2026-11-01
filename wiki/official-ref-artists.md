Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A music artist.

#### Resource `artists`
| Attribute | Type | Description |
|---|---|---|
| `backgroundColor` (optional) | string | Artist profile background colour override |
| `contributionsEnabled` (optional) | boolean | Is the artist enabled for contributions? |
| `contributionsSalesPitch` (optional) | string | Contributions sales pitch |
| `externalLinks` (optional) | External_Link[] | Artist links external to TIDAL API |
| `foregroundColor` (optional) | string | Artist profile foreground colour override |
| `handle` (optional) | string | Artist handle |
| `name` | string | Artist name |
| `numberOfFollowers` (optional) | integer (int32) | Number of users in the followers relationship |
| `ownerType` (optional) | string (LABEL, USER, MIXED) | Ownership type of the artist profile. LABEL: label-managed profile, USER: user-created profile, MIXED: claimed profile with both label and user content. May be null during rollout/backfill. |
| `popularity` | number (double) | Artist popularity (0.0 - 1.0) |
| `spotlighted` (optional) | boolean | Is the artist spotlighted? |

Relationships (`include=`): `albums`, `bannerArt`, `biography`, `claimStatus`, `followers`, `following`, `logoArt`, `owners`, `profileArt`, `radio`, `roles`, `similarArtists`, `trackProviders`, `tracks`, `videos`

### Get multiple artists
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple artists by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[handle]` | query |  | string[] | Artist handle (e.g. `jayz`) |
| `filter[id]` | query |  | string[] | List of artist IDs (e.g. `1566`) |
| `filter[owners.id]` | query |  | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, bannerArt, biography, claimStatus, followers, following, logoArt, owners, profileArt, radio, roles, similarArtists, trackProviders, tracks, videos |
| `includeLinkage` | query |  | string[]: albums, bannerArt, biography, claimStatus, followers, following, logoArt, owners, profileArt, radio, roles, similarArtists, trackProviders, tracks, videos | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single artist
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/artists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new artist.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "handle?": "string",
      "name": "string"
    },
    "type": "artists"
  },
  "meta?": {
    "dryRun?": "boolean"
  }
}
```
`?` = optional
##### Responses
`200` Successful dry run, `201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single artist
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single artist by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, bannerArt, biography, claimStatus, followers, following, logoArt, owners, profileArt, radio, roles, similarArtists, trackProviders, tracks, videos |
| `includeLinkage` | query |  | string[]: albums, bannerArt, biography, claimStatus, followers, following, logoArt, owners, profileArt, radio, roles, similarArtists, trackProviders, tracks, videos | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single artist
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artists/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

When both profile colours are available, they must have at least 3:1 contrast.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "backgroundColor?": "string",
      "contributionsEnabled?": "boolean",
      "contributionsSalesPitch?": "string",
      "externalLinks?": [
        {
          "href?": "string (uri)",
          "meta": {
            "type": "TIDAL_SHARING | TIDAL_USER_SHARING | TIDAL_AUTOPLAY_ANDROID | TIDAL_AUTOPLAY_IOS | TIDAL_AUTOPLAY_WEB | TWITTER | FACEBOOK | INSTAGRAM | TIKTOK | SNAPCHAT | OFFICIAL_HOMEPAGE | CASHAPP_CONTRIBUTIONS | ARTIST_CLAIM_PROVIDER_REDIRECT | STRIPE_AUTHORIZATION_REDIRECT | SQUARE_AUTHORIZATION_REDIRECT"
          }
        }
      ],
      "foregroundColor?": "string",
      "handle?": "string",
      "name?": "string"
    },
    "id": "string",
    "type": "artists"
  },
  "meta?": {
    "dryRun?": "boolean"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get albums relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/albums```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves albums relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albums |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get bannerArt relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/bannerArt```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Reads the selected header banner artwork.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: bannerArt |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update bannerArt relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/bannerArt```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Selects one owned, attachable IMAGE artwork by ID, replacing the selection. Empty data clears the selection; null data and more than one entry are rejected. Previous artwork no longer selected by profileArt, bannerArt or logoArt is soft-deleted unless system-managed. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artworks"
    }
  ],
  "meta?": {
    "mode?": "REPLACE_ALL"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get biography relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/biography```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves biography relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: biography |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get claimStatus relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/claimStatus```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves claimStatus relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `include` | query |  | string[] | Include related resources. Available relationships: claimStatus |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get followers relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/followers```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves followers relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `include` | query |  | string[] | Include related resources. Available relationships: followers |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: followers.albums |
| `viewerContext` | query |  | string |  |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from following relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/following```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes item(s) from following relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artists"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get following relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/following```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves following relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `include` | query |  | string[] | Include related resources. Available relationships: following |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: following.albums |
| `viewerContext` | query |  | string |  |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Add to following relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/following```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Adds item(s) to following relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artists"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get logoArt relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/logoArt```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Reads the selected logo artwork.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: logoArt |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update logoArt relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/logoArt```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Selects one owned, attachable IMAGE artwork by ID, replacing the selection. Empty data clears the selection; null data and more than one entry are rejected. Previous artwork no longer selected by profileArt, bannerArt or logoArt is soft-deleted unless system-managed. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artworks"
    }
  ],
  "meta?": {
    "mode?": "REPLACE_ALL"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/owners```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get profileArt relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/profileArt```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Reads the artist's avatar artwork.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: profileArt |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update profileArt relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/profileArt```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Replaces the artist's uploaded avatar selection with one owned, attachable artwork. Empty data clears the uploaded selection; legacy pictures or album fallback artwork may still appear in profileArt. Previous artwork no longer selected by profileArt, bannerArt or logoArt is soft-deleted unless system-managed. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artworks"
    }
  ],
  "meta?": {
    "mode?": "REPLACE_ALL"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get radio relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/radio```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves radio relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: radio |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: radio.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get roles relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/roles```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves roles relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `include` | query |  | string[] | Include related resources. Available relationships: roles |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get similarArtists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/similarArtists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves similarArtists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: similarArtists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: similarArtists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get trackProviders relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/trackProviders```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves trackProviders relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `include` | query |  | string[] | Include related resources. Available relationships: trackProviders |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get tracks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/tracks```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves tracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `collapseBy` | query | yes | string: FINGERPRINT, NONE | Collapse by options for getting artist tracks. Available options: FINGERPRINT, ID. FINGERPRINT option might collapse similar tracks based entry fingerprints while collapsing by ID always returns all available items. |
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: tracks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: tracks |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get videos relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artists/{id}/relationships/videos```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves videos relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: videos |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: videos |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
