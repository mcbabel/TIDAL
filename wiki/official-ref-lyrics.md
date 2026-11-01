Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Lyrics for a track, including plain text and time-synced LRC formats.

#### Resource `lyrics`
| Attribute | Type | Description |
|---|---|---|
| `direction` (optional) | string (LEFT_TO_RIGHT, RIGHT_TO_LEFT) |  |
| `lrcText` (optional) | string |  |
| `provider` (optional) | LyricsProvider |  |
| `technicalStatus` | string (PENDING, PROCESSING, ERROR, OK) |  |
| `text` (optional) | string |  |

Relationships (`include=`): `owners`, `track`

### Create single lyric
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/lyrics```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new lyric.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes?": {
      "text?": "string"
    },
    "relationships": {
      "track": {
        "data?": {
          "id": "string",
          "type": "tracks"
        },
        "id?": "string",
        "type?": "tracks"
      }
    },
    "type": "lyrics"
  },
  "meta?": {
    "generate?": "boolean"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single lyric
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/lyrics/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Deletes existing lyric.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Lyrics Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single lyric
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/lyrics/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single lyric by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Lyrics Id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners, track |
| `includeLinkage` | query |  | string[]: owners, track | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: track |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single lyric
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/lyrics/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Updates existing lyric.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Lyrics Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "lrcText?": "string",
      "text?": "string"
    },
    "id": "string",
    "type": "lyrics"
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
```https://openapi.tidal.com/v2/lyrics/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Lyrics Id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get track relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/lyrics/{id}/relationships/track```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves track relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Lyrics Id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: track |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: track |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
