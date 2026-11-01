Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's weekly update schedule for an AI-created playlist.

#### Resource `playlistGenerationSchedules`
| Attribute | Type | Description |
|---|---|---|
| `configurationVersion` | integer (int32) |  |
| `createdAt` | string (date-time) |  |
| `frequency` | string (WEEKLY) | Recurrence frequency defined by RFC 5545 |
| `lastModifiedAt` | string (date-time) |  |
| `status` | string (ACTIVE, DISABLED, DELETING, PROVISIONING, UPDATING, ERROR, UNKNOWN) |  |
| `timeZone` | string | IANA Time Zone Database identifier used to evaluate local civil time. |
| `weekday` | string (MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY, SATURDAY, SUNDAY) |  |

Relationships (`include=`): `playlist`

### Get multiple playlistGenerationSchedules
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerationSchedules```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

Retrieves multiple playlistGenerationSchedules by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[playlist.id]` | query | yes | string[] | Playlist id (e.g. `550e8400-e29b-41d4-a716-446655440000`) |
| `include` | query |  | string[] | Include related resources. Available relationships: playlist |
| `includeLinkage` | query |  | string[]: playlist | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: playlist.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single playlistGenerationSchedule
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlistGenerationSchedules```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

Creates a new playlistGenerationSchedule.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "timeZone": "string",
      "weekday": "MONDAY | TUESDAY | WEDNESDAY | THURSDAY | FRIDAY | SATURDAY | SUNDAY"
    },
    "relationships": {
      "playlist": {
        "data": {
          "id": "string",
          "type": "playlists"
        }
      }
    },
    "type": "playlistGenerationSchedules"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single playlistGenerationSchedule
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playlistGenerationSchedules/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

Deletes existing playlistGenerationSchedule.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string |  |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single playlistGenerationSchedule
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerationSchedules/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

Retrieves single playlistGenerationSchedule by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string |  |
| `include` | query |  | string[] | Include related resources. Available relationships: playlist |
| `includeLinkage` | query |  | string[]: playlist | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: playlist.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single playlistGenerationSchedule
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlistGenerationSchedules/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

Updates existing playlistGenerationSchedule.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string |  |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "timeZone?": "string",
      "weekday?": "MONDAY | TUESDAY | WEDNESDAY | THURSDAY | FRIDAY | SATURDAY | SUNDAY"
    },
    "id": "string",
    "type": "playlistGenerationSchedules"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get playlist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerationSchedules/{id}/relationships/playlist```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

Retrieves playlist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string |  |
| `include` | query |  | string[] | Include related resources. Available relationships: playlist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: playlist.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
