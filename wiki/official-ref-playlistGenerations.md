Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An immutable generation attempt targeting a user playlist.

#### Resource `playlistGenerations`
| Attribute | Type | Description |
|---|---|---|
| `lastGeneratedAt` (optional) | string (date-time) | Datetime the playlist content this generation produced was committed (ISO 8601). Unlike progress.lastModifiedAt, which any write moves, this only moves when a generation succeeds. Omitted while a generation is still running, when it failed, and for playlists generated before generation history was recorded |
| `preferenceVersion` | integer (int32) | Track-preference version snapshotted by this generation |
| `progress` | PlaylistGenerationProgress | Recoverable AI playlist generation progress snapshot |
| `prompt` (optional) | string | Prompt used to create the generation; omitted for legacy generations |
| `status` | string (PENDING, PROCESSING, ERROR, OK) | Current prompted-playlist generation status |

Relationships (`include=`): `baseGeneration`, `playlist`, `trackPreferences`

### Get multiple playlistGenerations
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves multiple playlistGenerations by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[playlist.id]` | query | yes | string[] | Playlist id (e.g. `550e8400-e29b-41d4-a716-446655440000`) |
| `generationView` | query |  | string: CURRENT, LATEST | CURRENT selects the committed generation. LATEST selects the newest accepted attempt, regardless of status. New values may be added at any time. |
| `include` | query |  | string[] | Include related resources. Available relationships: baseGeneration, playlist, trackPreferences |
| `includeLinkage` | query |  | string[]: baseGeneration, playlist, trackPreferences | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: baseGeneration.trackPreferences |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single playlistGeneration
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `201` (write test with cleanup).

Creates a new playlistGeneration.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "preferenceVersion?": "integer (int32)",
      "prompt": "string"
    },
    "relationships": {
      "baseGeneration?": {
        "data": {
          "id": "string",
          "type": "playlistGenerations"
        }
      },
      "playlist": {
        "data": {
          "id": "string",
          "type": "playlists"
        }
      }
    },
    "type": "playlistGenerations"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single playlistGeneration
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves single playlistGeneration by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `include` | query |  | string[] | Include related resources. Available relationships: baseGeneration, playlist, trackPreferences |
| `includeLinkage` | query |  | string[]: baseGeneration, playlist, trackPreferences | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: baseGeneration.trackPreferences |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get baseGeneration relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}/relationships/baseGeneration```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves baseGeneration relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `include` | query |  | string[] | Include related resources. Available relationships: baseGeneration |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: baseGeneration.trackPreferences |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get playlist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}/relationships/playlist```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves playlist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `include` | query |  | string[] | Include related resources. Available relationships: playlist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: playlist.items |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from trackPreferences relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}/relationships/trackPreferences```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Removes feedback for one track without removing the track from the playlist. An absent entry is unchanged. Returns an acknowledgement; read the relationship again for its current preference version. Requires the current meta.preferenceVersion as meta.expectedPreferenceVersion; stale versions return 409.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "tracks"
    }
  ],
  "meta": {
    "expectedPreferenceVersion": "integer (int32)"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get trackPreferences relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}/relationships/trackPreferences```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Retrieves trackPreferences relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `include` | query |  | string[] | Include related resources. Available relationships: trackPreferences |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: trackPreferences |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update trackPreferences relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}/relationships/trackPreferences```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Incrementally updates feedback for one existing track preference, leaving other entries unchanged. Empty data is rejected; a missing entry returns 409. Returns the complete preference snapshot. Requires the current meta.preferenceVersion as meta.expectedPreferenceVersion; stale versions return 409.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta": {
        "preference": "KEEP | REMOVE | MORE_LIKE_THIS"
      },
      "type": "tracks"
    }
  ],
  "meta": {
    "expectedPreferenceVersion": "integer (int32)",
    "mode?": "INCREMENTAL"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Add to trackPreferences relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlistGenerations/{id}/relationships/trackPreferences```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Adds feedback for one track. An existing entry is unchanged, including its preference. Returns the complete preference snapshot. All writes require the current meta.preferenceVersion as meta.expectedPreferenceVersion; stale versions return 409.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist generation id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta": {
        "preference": "KEEP | REMOVE | MORE_LIKE_THIS"
      },
      "type": "tracks"
    }
  ],
  "meta": {
    "expectedPreferenceVersion": "integer (int32)"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
