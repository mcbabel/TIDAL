Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A music album, consisting of one or more tracks.

#### Resource `albums`
| Attribute | Type | Description |
|---|---|---|
| `accessType` (optional) | string (PUBLIC, UNLISTED, PRIVATE) | Access type |
| `ai` (optional) | boolean | Whether the album is AI-generated |
| `albumType` | string (ALBUM, EP, SINGLE) | Album type |
| `availability` (optional) | string[] (STREAM, DJ, STEM) | Available usage for this album. Deprecated: use 'usageRules' instead. This field will be removed in a future version. **Deprecated.** |
| `barcodeId` | string |  |
| `copyright` (optional) | Copyright | Copyright information |
| `createdAt` (optional) | string (date-time) | Datetime of album creation (ISO 8601) |
| `duration` | string | Duration (ISO 8601) |
| `explicit` | boolean | Explicit content |
| `externalLinks` (optional) | External_Link[] | Album links external to TIDAL API |
| `mediaTags` | string[] |  |
| `numberOfItems` | integer (int32) | Number of items in album |
| `numberOfVolumes` | integer (int32) | Number of volumes |
| `popularity` | number (double) | Popularity (0.0 - 1.0) |
| `published` (optional) | boolean | Whether the album is published and available to everyone. Present only for uploaded albums. |
| `releaseDate` (optional) | string (date) | Release date (ISO-8601) |
| `title` | string | Album title |
| `type` (optional) | string (ALBUM, EP, SINGLE) | Album type. Deprecated: use 'albumType' instead. This field will be removed in a future version. **Deprecated.** |
| `version` (optional) | string | Album version |

Relationships (`include=`): `albumStatistics`, `artists`, `coverArt`, `genres`, `items`, `owners`, `priceConfig`, `providers`, `replacement`, `shares`, `similarAlbums`, `suggestedCoverArts`, `usageRules`

### Get multiple albums
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple albums by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[barcodeId]` | query |  | string[] | List of barcode IDs (EAN-13 or UPC-A). NOTE: Supplying more than one barcode ID will currently only return one album per barcode ID. (e.g. `196589525444`) |
| `filter[id]` | query |  | string[] | List of album IDs (e.g. `251380836`) |
| `filter[owners.id]` | query |  | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: albumStatistics, artists, coverArt, genres, items, owners, priceConfig, providers, replacement, shares, similarAlbums, suggestedCoverArts, usageRules |
| `includeLinkage` | query |  | string[]: albumStatistics, artists, coverArt, genres, items, owners, priceConfig, providers, replacement, shares, similarAlbums, suggestedCoverArts, usageRules | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
| `sort` | query |  | string[]: createdAt, -createdAt, title, -title | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single album
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/albums```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates an uploaded album. Album creation is not atomic with its artist assignment, so every listed artist must be owned by the caller; a collaborator or album-level grant is not enough until the album exists.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "albumType?": "ALBUM | EP | SINGLE",
      "copyright?": {
        "text": "string"
      },
      "explicit?": "boolean",
      "explicitLyrics?": "boolean",
      "releaseDate?": "string (date)",
      "title": "string",
      "version?": "string"
    },
    "relationships": {
      "artists": {
        "data": [
          {
            "id": "string",
            "type": "artists"
          }
        ]
      },
      "genres?": {
        "data": [
          {
            "id": "string",
            "type": "genres"
          }
        ]
      }
    },
    "type": "albums"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single album
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/albums/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes existing album.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single album
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single album by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albumStatistics, artists, coverArt, genres, items, owners, priceConfig, providers, replacement, shares, similarAlbums, suggestedCoverArts, usageRules |
| `includeLinkage` | query |  | string[]: albumStatistics, artists, coverArt, genres, items, owners, priceConfig, providers, replacement, shares, similarAlbums, suggestedCoverArts, usageRules | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single album
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/albums/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Updates existing album.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes?": {
      "accessType?": "PUBLIC | UNLISTED | PRIVATE",
      "albumType?": "ALBUM | EP | SINGLE",
      "barcodeId?": "string",
      "copyright?": {
        "text": "string"
      },
      "explicit?": "boolean",
      "explicitLyrics?": "boolean",
      "releaseDate?": "string (date)",
      "title?": "string",
      "version?": "string"
    },
    "id": "string",
    "relationships?": {
      "genres?": {
        "data": [
          {
            "id": "string",
            "type": "genres"
          }
        ]
      }
    },
    "type": "albums"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get albumStatistics relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/albumStatistics```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves albumStatistics relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `include` | query |  | string[] | Include related resources. Available relationships: albumStatistics |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/artists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: artists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artists.albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update artists relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/artists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Sets the album's artists, replacing the current list. Artists are listed in the order given. Provide 1 to 10 distinct artists. You can add your own artist profile and the profiles of users who have owner or collaborator access to the album. Only the album's owner can change its artists. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artists"
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

### Get coverArt relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/coverArt```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves coverArt relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: coverArt |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update coverArt relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/coverArt```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Replaces the uploaded cover artwork selection with one attachable artwork. Empty data clears the selection. Previously attached uploaded artwork is soft-deleted unless system-managed. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
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

### Get genres relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/genres```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves genres relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: genres |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get items relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update items relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Incrementally updates one existing track's 1-based track number to meta.positionIndex. Does not replace the album's items or add or remove tracks. Empty data is rejected. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks | videos"
    }
  ],
  "meta": {
    "mode?": "INCREMENTAL",
    "positionIndex": "integer (int32)"
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
```https://openapi.tidal.com/v2/albums/{id}/relationships/owners```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get priceConfig relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/priceConfig```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves priceConfig relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: priceConfig |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get providers relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/providers```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves providers relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: providers |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get replacement relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/replacement```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves replacement relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: replacement |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: replacement |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get shares relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/shares```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

The album's share links, active and expired, newest first.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `include` | query |  | string[] | Include related resources. Available relationships: shares |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: shares.sharedResources |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get similarAlbums relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/similarAlbums```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves similarAlbums relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: similarAlbums |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: similarAlbums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get suggestedCoverArts relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/suggestedCoverArts```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves suggestedCoverArts relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `include` | query |  | string[] | Include related resources. Available relationships: suggestedCoverArts |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get usageRules relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/albums/{id}/relationships/usageRules```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves usageRules relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Album id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: usageRules |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
