Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An emoji reaction by a user on a piece of content.

#### Resource `reactions`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` | string (date-time) | Datetime of the reaction creation (ISO 8601) |
| `emoji` | string | The type of reaction representing an emoji |

Relationships (`include=`): `author`, `ownerProfiles`, `owners`

### Get multiple reactions
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/reactions```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves multiple reactions by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[emoji]` | query |  | string[] | Filter by emoji (e.g. `👍`) |
| `filter[subject.id]` | query |  | string[] | Deprecated: use filter[subject]. Filter by subject resource ID (e.g. `12345`) **Deprecated.** |
| `filter[subject.type]` | query |  | string[]: albums, tracks, artists, videos, playlists, comments, trackSourceFiles | Deprecated: use filter[subject]. Filter by subject resource type (e.g. `albums`) **Deprecated.** |
| `filter[subject]` | query |  | string | The subject whose reactions to return. Use either subject or the deprecated subject.id and subject.type pair. |
| `include` | query |  | string[] | Include related resources. Available relationships: author, ownerProfiles, owners |
| `includeLinkage` | query |  | string[]: author, ownerProfiles, owners | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: author.albums |
| `stats` | query |  | string: ALL, COUNTS_BY_TYPE, TOTAL_COUNT |  |
| `statsOnly` | query |  | boolean |  |
| `viewerContext` | query |  | string |  |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single reaction
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/reactions```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new reaction.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "emoji": "string"
    },
    "relationships": {
      "subject": {
        "data": {
          "id": "string",
          "type": "albums | tracks | artists | videos | playlists | comments | trackSourceFiles"
        }
      }
    },
    "type": "reactions"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single reaction
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/reactions/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Deletes existing reaction.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Reaction Id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get author relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/reactions/{id}/relationships/author```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

The artist who left the reaction.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Reaction Id |
| `include` | query |  | string[] | Include related resources. Available relationships: author |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: author.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get ownerProfiles relationship ("to-many") (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/reactions/{id}/relationships/ownerProfiles```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Deprecated. Use author for attribution.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Reaction Id |
| `include` | query |  | string[] | Include related resources. Available relationships: ownerProfiles |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/reactions/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Reaction Id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
