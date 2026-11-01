Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A record of the user's decision on an announced price change.

#### Resource `subscriptionPriceChangeDecisions`
| Attribute | Type | Description |
|---|---|---|
| `decidedAt` (optional) | string (date-time) | When the user decided. Absent when the consent was implicit (derived from the subscription start). |
| `status` | string (ACCEPTED, REJECTED) | The user's decision. ACCEPTED is permanent; REJECTED can still be flipped to ACCEPTED before the renewal. |

Relationships (`include=`): `priceChange`

### Get multiple subscriptionPriceChangeDecisions
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/subscriptionPriceChangeDecisions```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves multiple subscriptionPriceChangeDecisions by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: priceChange |
| `includeLinkage` | query |  | string[]: priceChange | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single subscriptionPriceChangeDecision
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/subscriptionPriceChangeDecisions```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new subscriptionPriceChangeDecision.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "status": "ACCEPTED | REJECTED"
    },
    "relationships": {
      "priceChange": {
        "data": {
          "id": "string",
          "type": "userSubscriptionPriceChanges"
        }
      }
    },
    "type": "subscriptionPriceChangeDecisions"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Update single subscriptionPriceChangeDecision
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/subscriptionPriceChangeDecisions/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Updates existing subscriptionPriceChangeDecision.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Price change decision id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "status": "ACCEPTED | REJECTED"
    },
    "id": "string",
    "type": "subscriptionPriceChangeDecisions"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get priceChange relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/subscriptionPriceChangeDecisions/{id}/relationships/priceChange```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves priceChange relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Price change decision id |
| `include` | query |  | string[] | Include related resources. Available relationships: priceChange |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
