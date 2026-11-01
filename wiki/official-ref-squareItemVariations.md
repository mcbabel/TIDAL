Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A variation in the seller's own Square catalog.

#### Resource `squareItemVariations`
| Attribute | Type | Description |
|---|---|---|
| `currency` | string (USD) |  |
| `name` | string | Variation name; may be empty |
| `price` (optional) | string | Amount in the currency's major units |
| `pricingType` | string (FIXED, VARIABLE) | Effective pricing mode at the selected site's shipping location (merchant-main fallback). Price is present only for FIXED when its amount is available |
| `revision` | integer (int64) | Square variation revision covering its catalog fields, including name, pricing, stock tracking and attached artworks; excludes inventory quantity and other variations |
| `stockQuantity` (optional) | integer (int64) | Units at the selected site's shipping location (merchant-main fallback); present only when tracked and available; may be negative |
| `stockTracked` | boolean | Whether Square tracks stock at the selected site's shipping location (merchant-main fallback) |

Relationships (`include=`): `artworks`, `owners`

### Commit atomic resource operations
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/operations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Atomic operations are only used to create Square shop catalog items (selling merchandise), see Square below.

Commits a supported group of resource creations together. Only add operations without ref or href are supported. Local linkage must reference an earlier creation. Each resource's mutation policy applies. After a timeout or server error, retry unchanged with the original Idempotency-Key. Replay is bounded by downstream receipt and idempotency retention.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header | yes | string | Retry an unchanged request with the original key after a timeout or server error. Replay is bounded by downstream receipt and idempotency retention. |
##### Body (`application/vnd.api+json;ext="https://jsonapi.org/ext/atomic"`)
``` yaml
{
  "atomic:operations": [
    {
      "data": {
        "attributes": {
          "name?": "string",
          "price": "string",
          "stockTracked": "boolean"
        },
        "lid?": "string",
        "relationships": {
          "items": {
            "data": [
              {
                "lid": "<object>",
                "type": "<object>"
              }
            ]
          }
        },
        "type": "squareItemVariations"
      },
      "op": "add"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Committed results, in the order of the requested operations, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Create single squareItemVariation
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/squareItemVariations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts.

Adds a fixed-price variation at the end of the item's display order, preserving all existing variations and their pricing modes. After a timeout or `5xx`, retry unchanged with the original Idempotency-Key. Replay protection is bounded by receipt availability and Square's idempotency retention.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "name?": "string",
      "price": "string",
      "stockTracked": "boolean"
    },
    "relationships": {
      "items": {
        "data": [
          {
            "id": "string",
            "type": "squareItems"
          }
        ]
      }
    },
    "type": "squareItemVariations"
  },
  "meta": {
    "expectedItemRevision": "integer (int64)"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single squareItemVariation
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/squareItemVariations/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes this variation by ID without a revision precondition, preserving its siblings. The last variation cannot be deleted; delete the item instead. Returns an acknowledgement; read the parent item for its current revision. After a timeout or `5xx`, retry unchanged with the original Idempotency-Key. Replay protection is bounded by receipt availability and Square's idempotency retention.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square variation id |
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single squareItemVariation
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareItemVariations/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); none exists for the account.

Retrieves single squareItemVariation by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square variation id |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks, owners |
| `includeLinkage` | query |  | string[]: artworks, owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Update single squareItemVariation
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/squareItemVariations/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates the variation's global name or its price and stock tracking at the selected site's shipping location, with merchant-main fallback. Stock quantity is changed through physical-count submissions. Price changes require existing positive fixed pricing at that location; name and stock tracking preserve other pricing modes. After a timeout or `5xx`, retry unchanged with the original Idempotency-Key. Replay protection is bounded by receipt availability and Square's idempotency retention.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square variation id |
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "name?": "string",
      "price?": "string",
      "stockTracked?": "boolean"
    },
    "id": "string",
    "type": "squareItemVariations"
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
```https://openapi.tidal.com/v2/squareItemVariations/{id}/relationships/artworks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); none exists for the account.

Artworks of the variation's Square catalog images in Square's display order. An image Square has no URL for stays in the list and its artwork has no files. Returns the variation revision the list was read at.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square variation id |
| `include` | query |  | string[] | Include related resources. Available relationships: artworks |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Update artworks relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/squareItemVariations/{id}/relationships/artworks```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID`. Not executed for real: it changes content, profiles or settings the test account does not own.

Replaces the variation's photos with the complete ordered list. Omitted photos are detached and stay in the seller's Square catalog; an empty list clears them. The first artwork is the primary photo. Duplicate artwork IDs are rejected. Uploaded TIDAL JPEG artworks, at most 15,000,000 bytes, are copied to Square and attached under new artwork IDs; their originals stay unchanged. Existing Square artworks must belong to this seller and are attached directly; they need not be the item's photos. Returns the complete resulting linkage in display order and the committed variation revision. Copies may remain in Square if the replacement fails. Retry unchanged with the original Idempotency-Key after a timeout or 5xx. Recovery is bounded by Marketplace receipts and Square's idempotency retention, and can be blocked if the variation is deleted or a source becomes unavailable or ineligible. Read the variation again to reconcile its current state.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square variation id |
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
```https://openapi.tidal.com/v2/squareItemVariations/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); none exists for the account.

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square variation id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
