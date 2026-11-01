Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Artwork images and videos used for albums, artists, tracks, and playlists.

#### Resource `artworks`
| Attribute | Type | Description |
|---|---|---|
| `files` | Artwork_File[] | Artwork files |
| `mediaType` | string (IMAGE, VIDEO) | Media type of artwork files |
| `sourceFile` (optional) | Artwork_SourceFile | Artwork source file |
| `visualMetadata` (optional) | Artwork_VisualMetadata | Color information extracted from artwork |

Relationships (`include=`): `owners`

### Get multiple artworks
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworks```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple artworks by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | Artwork id (e.g. `a468bee88def`) |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single artwork
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/artworks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new artwork.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "mediaType": "IMAGE | VIDEO",
      "sourceFile": {
        "md5Hash": "string",
        "size": "integer (int64)"
      }
    },
    "type": "artworks"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single artwork
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworks/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single artwork by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artwork id |
| `countryCode` | query |  | string | ISO 3166-1 alpha-2 country code |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworks/{id}/relationships/owners```
##### Access
Tier: `THIRD_PARTY` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artwork id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
