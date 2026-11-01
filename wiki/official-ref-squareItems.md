Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An item in the seller's own Square catalog. Create an item together with its initial variations through `POST /operations` using JSON:API Atomic Operations. Standalone `POST /squareItems` is not supported.

#### Resource `squareItems`
| Attribute | Type | Description |
|---|---|---|
| `currency` | string (USD) | Currency of every price on the item |
| `description` (optional) | string | Item description |
| `lastModifiedAt` (optional) | string (date-time) | Timestamp when the item was last modified in Square; absent when Square has not reported one |
| `origin` (optional) | string (TIDAL, OTHER) | Where the item was created |
| `publishedInSelectedSite` (optional) | boolean | Whether the item is published in the seller's selected Square Online site; false when no site is selected |
| `revision` | integer (int64) | Square catalog item revision used to guard item updates; excludes inventory stock |
| `title` | string | Item title; empty for an untitled item created in Square |

Relationships (`include=`): `artworks`, `owners`, `variations`

### Get multiple squareItems
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareItems```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** answered `403` `REQUIRED_TERMS_NOT_ACCEPTED: Latest terms and conditions must be accepted`.

Retrieves multiple squareItems by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `filter[origin]` | query |  | string: TIDAL, OTHER | Only items with this origin (e.g. `TIDAL`) |
| `filter[query]` | query |  | string | Word-prefix match on item titles, descriptions and abbreviations, and on variation names, SKUs and UPCs (e.g. `tee`) |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks, owners, variations |
| `includeLinkage` | query |  | string[]: artworks, owners, variations | Comma-separated direct relationships to return as linkage only, without related content. |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Delete single squareItem
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes existing squareItem.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single squareItem
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); terms not accepted (`403 REQUIRED_TERMS_NOT_ACCEPTED`).

Retrieves single squareItem by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks, owners, variations |
| `includeLinkage` | query |  | string[]: artworks, owners, variations | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Update single squareItem
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates existing squareItem.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "description?": "string",
      "title?": "string"
    },
    "id": "string",
    "type": "squareItems"
  },
  "meta": {
    "expectedRevision": "integer (int64)"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get artworks relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}/relationships/artworks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); terms not accepted (`403 REQUIRED_TERMS_NOT_ACCEPTED`).

A photo Square has no URL for stays in the list and its artwork has no files.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Update artworks relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}/relationships/artworks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Replaces the item's photos with the complete ordered list. Omitted photos are detached and stay in the seller's Square catalog; an empty list clears them. The first artwork is the primary photo. Duplicate artwork IDs are rejected. Uploaded TIDAL JPEG artworks, at most 15,000,000 bytes, are copied to Square and attached under new artwork IDs; their originals stay unchanged. Existing Square artworks must belong to this seller and are attached directly. Returns the complete resulting linkage in display order and the committed item revision. Copies may remain in Square if the replacement fails. Retry unchanged with the original Idempotency-Key after a timeout or 5xx. Recovery is bounded by Marketplace receipts and Square's idempotency retention, and can be blocked if the item is deleted or a source becomes unavailable or ineligible. Read the item again to reconcile its current state.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artworks"
    }
  ],
  "meta": {
    "expectedRevision": "integer (int64)",
    "mode?": "REPLACE_ALL"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `413`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); terms not accepted (`403 REQUIRED_TERMS_NOT_ACCEPTED`).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get variations relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}/relationships/variations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); terms not accepted (`403 REQUIRED_TERMS_NOT_ACCEPTED`).

Variations in Square's display order.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `include` | query |  | string[] | Include related resources. Available relationships: variations |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Update variations relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/squareItems/{id}/relationships/variations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Incrementally moves the selected variations as an ordered block before positionBefore, or to the end when omitted. Memberships are preserved; unselected variations retain their metadata and relative order. Empty data is rejected. Returns the affected linkage only and the updated item revision. After a timeout or `5xx`, retry unchanged with the original Idempotency-Key. Replay protection is bounded by receipt availability and Square's idempotency retention.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square item id |
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "squareItemVariations"
    }
  ],
  "meta": {
    "expectedRevision": "integer (int64)",
    "mode?": "INCREMENTAL",
    "positionBefore?": "string"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
