Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A Square Online site belonging to the seller's Square account.

#### Resource `squareSites`
| Attribute | Type | Description |
|---|---|---|
| `domain` (optional) | string | The site's domain, if one is configured |
| `published` (optional) | boolean | Whether the site is published on Square Online |
| `siteTitle` (optional) | string | The site's title as set by the seller in Square |

Relationships (`include=`): `items`

### Delete from items relationship ("to-many")
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/squareSites/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be Base62 encoded`. Not executed for real: it changes content, profiles or settings the test account does not own.

Removes the items from the site; they stay in the catalog. Items not published and repeated items are left alone. An item missing from the catalog fails the request before anything changes.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square Online site id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "squareItems"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get items relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/squareSites/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Square shop); none exists for the account.

Items published in the site, in title order. Missing catalog scopes return MISSING_ITEMS_SCOPE. A page can be short or empty and still have a next cursor.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square Online site id |
| `include` | query |  | string[] | Include related resources. Available relationships: items |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `429`, `500`, `503`

### Add to items relationship ("to-many")
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/squareSites/{id}/relationships/items```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_RESOURCE_ID: Invalid resource ID: Must be Base62 encoded`. Not executed for real: it changes content, profiles or settings the test account does not own.

Publishes the items in the site. Items already published and repeated items are left alone. An item missing from the catalog fails the request before anything changes.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Square Online site id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "squareItems"
    }
  ]
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
