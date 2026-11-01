Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A physical inventory count recorded in Square, identified by its count reference. Its quantity describes stock at occurredAt, rather than current calculated stock after later inventory activity. Creation only; no resource reads or relationship navigation.

#### Resource `squareItemVariationPhysicalCounts`
| Attribute | Type | Description |
|---|---|---|
| `occurredAt` | string (date-time) |  |
| `quantity` | integer (int64) |  |
| `squareLocationId` | string | Square location where this physical count was recorded |

### Create single squareItemVariationPhysicalCount
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/squareItemVariationPhysicalCounts```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Records a whole-unit physical stock count at occurredAt. Requires stock tracking at the selected site's shipping location (merchant-main fallback). While its replay receipt remains available, exact retries retain the original location and event time. Catalog revisions do not guard inventory counts.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header | yes | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "occurredAt": "string (date-time)",
      "quantity": "integer (int64)"
    },
    "relationships": {
      "variations": {
        "data": [
          {
            "id": "string",
            "type": "squareItemVariations"
          }
        ]
      }
    },
    "type": "squareItemVariationPhysicalCounts"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `403`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
