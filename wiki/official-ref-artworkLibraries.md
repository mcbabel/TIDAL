Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A curated, TIDAL-owned set of artworks that users can attach as album or playlist cover art. Look a library up by name with `filter[name]`. A library exists once it has any entry; an unknown ID returns 404 and an unknown name returns no libraries. A library with no available artworks returns empty `artworks` and `randomArtwork`.

#### Resource `artworkLibraries`
| Attribute | Type | Description |
|---|---|---|
| `name` | string | Library name |

Relationships (`include=`): `artworks`, `randomArtwork`

### Get multiple artworkLibraries
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworkLibraries```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple artworkLibraries by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[name]` | query | yes | string[] | Library names (e.g. `album-defaults`) |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks, randomArtwork |
| `includeLinkage` | query |  | string[]: artworks, randomArtwork | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get single artworkLibrarie
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworkLibraries/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** not reached. No artwork library exists for the account (`/artworkLibraries/me` answers `404`).

Retrieves single artworkLibrarie by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artwork library ID |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks, randomArtwork |
| `includeLinkage` | query |  | string[]: artworks, randomArtwork | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artworks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworkLibraries/{id}/relationships/artworks```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** not reached. No artwork library exists for the account (`/artworkLibraries/me` answers `404`).

Artworks in the library that have finished processing and are not flagged or taken down, newest first
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artwork library ID |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get randomArtwork relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artworkLibraries/{id}/relationships/randomArtwork```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

**Live test 2026-11-01:** not reached. No artwork library exists for the account (`/artworkLibraries/me` answers `404`).

A random artwork from the library, used by clients to supply a default artwork, for example for albums without cover art. Picked per request from the artworks that have finished processing and are not flagged or taken down, and not stored; empty when there are none
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artwork library ID |
| `include` | query |  | string[] | Include related resources. Available relationships: randomArtwork |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
