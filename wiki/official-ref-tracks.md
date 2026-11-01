Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A music track.

#### Resource `tracks`
| Attribute | Type | Description |
|---|---|---|
| `accessType` (optional) | string (PUBLIC, UNLISTED, PRIVATE) | Access type |
| `ai` (optional) | boolean | Whether the track is AI-generated |
| `availability` (optional) | string[] (STREAM, DJ, STEM) | Available usage for this track. Deprecated: use 'usageRules' instead. This field will be removed in a future version. **Deprecated.** |
| `bpm` (optional) | number (float) | Beats per minute |
| `copyright` (optional) | Copyright | Copyright information |
| `createdAt` (optional) | string (date-time) | Datetime of track creation (ISO 8601) |
| `duration` | string | Duration (ISO 8601) |
| `explicit` | boolean | Explicit content |
| `externalLinks` (optional) | External_Link[] | Track links external to TIDAL API |
| `isrc` | string | International Standard Recording Code (ISRC) |
| `key` | string (UNKNOWN, C, CSharp, D, Eb, E, F, FSharp, G, Ab, A, Bb, B) | Key |
| `keyScale` | string (UNKNOWN, MAJOR, MINOR, AEOLIAN, BLUES, DORIAN, HARMONIC_MINOR, LOCRIAN, LYDIAN, MIXOLYDIAN, PENTATONIC_MAJOR, PHRYGIAN, MELODIC_MINOR, PENTATONIC_MINOR) | The scale of the key |
| `mediaTags` | string[] |  |
| `popularity` | number (double) | Popularity (0.0 - 1.0) |
| `spotlighted` (optional) | boolean | Is the track spotlighted? |
| `title` | string | Track title |
| `toneTags` (optional) | string[] |  |
| `version` (optional) | string | Track version, complements title |

Relationships (`include=`): `albums`, `artists`, `credits`, `download`, `genres`, `lyrics`, `metadataStatus`, `owners`, `priceConfig`, `providers`, `radio`, `replacement`, `shares`, `similarTracks`, `sourceFile`, `suggestedTracks`, `trackStatistics`, `usageRules`

### Get multiple tracks
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple tracks by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[id]` | query |  | string[] | List of track IDs (e.g. `75413016`) |
| `filter[isrc]` | query |  | string[] | List of ISRCs. When a single ISRC is provided, pagination is supported and multiple tracks may be returned. When multiple ISRCs are provided, one track per ISRC is returned without pagination. (e.g. `QMJMT1701237`) |
| `filter[owners.id]` | query |  | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, artists, credits, download, genres, lyrics, metadataStatus, owners, priceConfig, providers, radio, replacement, shares, similarTracks, sourceFile, suggestedTracks, trackStatistics, usageRules |
| `includeLinkage` | query |  | string[]: albums, artists, credits, download, genres, lyrics, metadataStatus, owners, priceConfig, providers, radio, replacement, shares, similarTracks, sourceFile, suggestedTracks, trackStatistics, usageRules | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
| `sort` | query |  | string[]: createdAt, -createdAt, title, -title | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single track
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/tracks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Creates uploads (albums, tracks, audio source files, artwork) on TIDAL. Needs real media files and the rights to publish them; uploads can become visible to other users.

Creates a new track.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "accessType": "PUBLIC | UNLISTED | PRIVATE",
      "explicit?": "boolean",
      "title": "string"
    },
    "relationships": {
      "albums": {
        "data": [
          {
            "id": "string",
            "type": "albums"
          }
        ]
      },
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
    "type": "tracks"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single track
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a positive integer`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes existing track.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single track
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single track by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albums, artists, credits, download, genres, lyrics, metadataStatus, owners, priceConfig, providers, radio, replacement, shares, similarTracks, sourceFile, suggestedTracks, trackStatistics, usageRules |
| `includeLinkage` | query |  | string[]: albums, artists, credits, download, genres, lyrics, metadataStatus, owners, priceConfig, providers, radio, replacement, shares, similarTracks, sourceFile, suggestedTracks, trackStatistics, usageRules | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single track
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a positive integer`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates existing track.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes?": {
      "accessType?": "PUBLIC | UNLISTED | PRIVATE",
      "bpm?": "number (float)",
      "explicit?": "boolean",
      "isrc?": "string",
      "key?": "UNKNOWN | C | CSharp | D | Eb | E | F | FSharp | G | Ab | A | Bb | B",
      "keyScale?": "UNKNOWN | MAJOR | MINOR | AEOLIAN | BLUES | DORIAN | HARMONIC_MINOR | LOCRIAN | LYDIAN | MIXOLYDIAN | PENTATONIC_MAJOR | PHRYGIAN | MELODIC_MINOR | PENTATONIC_MINOR",
      "title?": "string",
      "toneTags?": [
        "string"
      ]
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
    "type": "tracks"
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
```https://openapi.tidal.com/v2/tracks/{id}/relationships/albums```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves albums relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: albums |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update albums relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/albums```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a positive integer`. Not executed for real: it changes content, profiles or settings the test account does not own.

Moves the uploaded track to the supplied album, replacing its previous album association. Exactly one album is required; empty data cannot clear it. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "albums"
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

### Get artists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/artists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves artists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
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
```https://openapi.tidal.com/v2/tracks/{id}/relationships/artists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be a positive integer`. Not executed for real: it changes content, profiles or settings the test account does not own.

Sets the track's artists, replacing the current list. Artists are listed in the order given. Provide 1 to 10 distinct artists. You can add your own artist profile and the profiles of users who have owner or collaborator access to the track or its album. Only the track's owner can change its artists. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
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

### Get credits relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/credits```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves credits relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: credits |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: credits.artist.albums |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get download relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/download```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves download relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: download |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get genres relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/genres```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves genres relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: genres |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get lyrics relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/lyrics```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves lyrics relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: lyrics |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: lyrics.track |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get metadataStatus relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/metadataStatus```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves metadataStatus relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: metadataStatus |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/owners```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** answered `404` `NOT_FOUND: Resource not found`. Expected: this relationship only exists for own (uploaded) content or the owner.

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get priceConfig relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/priceConfig```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves priceConfig relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: priceConfig |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get providers relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/providers```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves providers relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: providers |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get radio relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/radio```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves radio relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: radio |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: radio.items |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get replacement relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/replacement```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves replacement relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
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
```https://openapi.tidal.com/v2/tracks/{id}/relationships/shares```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** answered `404` `NOT_FOUND: Resource not found`. Expected: this relationship only exists for own (uploaded) content or the owner.

The track's share links, active and expired, newest first.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: shares |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: shares.sharedResources |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get similarTracks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/similarTracks```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves similarTracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: similarTracks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: similarTracks |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get sourceFile relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/sourceFile```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves sourceFile relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: sourceFile |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get suggestedTracks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/suggestedTracks```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves suggestedTracks relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: suggestedTracks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: suggestedTracks |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get trackStatistics relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/trackStatistics```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves trackStatistics relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `include` | query |  | string[] | Include related resources. Available relationships: trackStatistics |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get usageRules relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/tracks/{id}/relationships/usageRules```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves usageRules relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Track id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: usageRules |
| `shareCode` | query |  | string | Share code used as a bearer credential for the resource. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
