Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A curated or user-created playlist of tracks and videos.

#### Resource `playlists`
| Attribute | Type | Description |
|---|---|---|
| `accessType` | string (PUBLIC, UNLISTED, PRIVATE) | Access type |
| `bounded` | boolean | Indicates if the playlist has a duration and set number of tracks |
| `createdAt` | string (date-time) | Datetime of playlist creation (ISO 8601) |
| `description` (optional) | string | Playlist description |
| `duration` (optional) | string | Duration of playlist (ISO 8601) |
| `externalLinks` | External_Link[] |  |
| `hasGenerations` (optional) | boolean | Whether the playlist has AI generations |
| `lastModifiedAt` | string (date-time) | Datetime of last modification of the playlist (ISO 8601) |
| `name` | string | Playlist name |
| `numberOfFollowers` | integer (int32) | The amount of followers of the playlist |
| `numberOfItems` (optional) | integer (int32) | Number of items in the items relationship |
| `numberOfTrackItems` (optional) | integer (int32) | Number of track items in the items relationship |
| `numberOfVideoItems` (optional) | integer (int32) | Number of video items in the items relationship |
| `playlistType` | string (EDITORIAL, USER, MIX, ARTIST) | The type of the playlist |

Relationships (`include=`): `collaboratorProfiles`, `collaborators`, `coverArt`, `curators`, `items`, `ownerProfiles`, `owners`, `suggestedCoverArts`

### Get multiple playlists
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `playlists.read`, `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple playlists by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[collaborators.id]` | query |  | string[] | User id. Also accepts `me`. |
| `filter[id]` | query |  | string[] | List of playlist IDs (e.g. `550e8400-e29b-41d4-a716-446655440000`) |
| `filter[owners.id]` | query |  | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: collaboratorProfiles, collaborators, coverArt, curators, items, ownerProfiles, owners, suggestedCoverArts |
| `includeLinkage` | query |  | string[]: collaboratorProfiles, collaborators, coverArt, curators, items, ownerProfiles, owners, suggestedCoverArts | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: curators.albums |
| `sort` | query |  | string[]: createdAt, -createdAt, lastModifiedAt, -lastModifiedAt, name, -name | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single playlist
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlists```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `201` (write test with cleanup).

Creates a new playlist.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "accessType?": "PUBLIC | UNLISTED",
      "createdAt?": "string (date-time)",
      "description?": "string",
      "name": "string"
    },
    "type": "playlists"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single playlist
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Deletes existing playlist.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single playlist
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves single playlist by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: collaboratorProfiles, collaborators, coverArt, curators, items, ownerProfiles, owners, suggestedCoverArts |
| `includeLinkage` | query |  | string[]: collaboratorProfiles, collaborators, coverArt, curators, items, ownerProfiles, owners, suggestedCoverArts | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: curators.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single playlist
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Updates existing playlist.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "accessType?": "PUBLIC | UNLISTED",
      "description?": "string",
      "name?": "string"
    },
    "id": "string",
    "type": "playlists"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete from collaboratorProfiles relationship ("to-many") (Deprecated)
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/collaboratorProfiles```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_REQUEST_BODY: Size must be between 1 and 20`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes item(s) from collaboratorProfiles relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
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

### Get collaboratorProfiles relationship ("to-many") (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/collaboratorProfiles```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Deprecated. Use curators for attribution.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `include` | query |  | string[] | Include related resources. Available relationships: collaboratorProfiles |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get collaborators relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/collaborators```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** answered `404` `NOT_FOUND: Resource not found`. Expected: this relationship only exists for own (uploaded) content or the owner.

Retrieves collaborators relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `include` | query |  | string[] | Include related resources. Available relationships: collaborators |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get coverArt relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/coverArt```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves coverArt relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: coverArt |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update coverArt relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/coverArt```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_REQUEST_BODY: Must not be null`. Not executed for real: it changes content, profiles or settings the test account does not own.

Replaces the custom cover artwork selection with one attachable artwork. Empty data clears the custom selection. Previously attached uploaded artwork is soft-deleted unless system-managed. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
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

### Get curators relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/curators```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Artist profiles credited for the playlist
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `include` | query |  | string[] | Include related resources. Available relationships: curators |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: curators.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Delete from items relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Deletes item(s) from items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta": {
        "itemId": "string"
      },
      "type": "tracks | videos"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get items relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `filter[query]` | query |  | string | Filter playlist items by a free-text query (e.g. `halo`) |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: items |
| `sort` | query |  | string[]: addedAt, -addedAt, albums.title, -albums.title, artists.name, -artists.name, duration, -duration, itemIndex, -itemIndex, title, -title | Values prefixed with "-" are sorted descending; values without it are sorted ascending. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update items relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Incrementally moves the occurrences selected by data[].meta.itemId before meta.positionBefore, or to the end when meta is omitted. Preserves unselected memberships, their metadata and relative order; no items are added or removed. Empty data is rejected. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta": {
        "itemId": "string"
      },
      "type": "tracks | videos"
    }
  ],
  "meta?": {
    "mode?": "INCREMENTAL",
    "positionBefore": "string"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Add to items relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/items```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `playlists.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Adds item(s) to items relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "meta?": {
        "addedAt?": "string (date-time)"
      },
      "type": "tracks | videos"
    }
  ],
  "meta?": {
    "onDuplicates?": "ADD | FAIL | SKIP",
    "positionBefore?": "string"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get ownerProfiles relationship ("to-many") (Deprecated)
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/ownerProfiles```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Deprecated. Use curators for attribution.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `include` | query |  | string[] | Include related resources. Available relationships: ownerProfiles |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/owners```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** answered `404` `NOT_FOUND: Resource not found`. Expected: this relationship only exists for own (uploaded) content or the owner.

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get suggestedCoverArts relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/playlists/{id}/relationships/suggestedCoverArts```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** answered `404` `NOT_FOUND: Resource not found`. Expected: this relationship only exists for own (uploaded) content or the owner.

Retrieves suggestedCoverArts relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Playlist id |
| `include` | query |  | string[] | Include related resources. Available relationships: suggestedCoverArts |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
