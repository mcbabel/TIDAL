Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A Stripe Connect account linked to a user for receiving payments.

#### Resource `stripeConnections`
| Attribute | Type | Description |
|---|---|---|
| `createdAt` (optional) | string (date-time) | Timestamp when the connection was created |
| `externalLinks` (optional) | External_Link[] | External links for Stripe connection |
| `lastModifiedAt` (optional) | string (date-time) | Timestamp when the connection was last modified |
| `status` | string (PENDING_REQUIREMENTS, UNDER_REVIEW, ACCEPTED, REJECTED, SUSPENDED) | Current status of this Stripe connection |

Relationships (`include=`): `owners`

### Get multiple stripeConnections
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/stripeConnections```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple stripeConnections by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single stripeConnection
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/stripeConnections```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Commerce: prices, Square shop and Stripe payment accounts. Connects or changes real sales and payment accounts.

Creates a new stripeConnection.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes?": {
      "integrationType?": "REDIRECT | EMBEDDED",
      "refreshUrl?": "string",
      "returnUrl?": "string"
    },
    "type": "stripeConnections"
  },
  "meta?": {
    "integrationType": "REDIRECT | EMBEDDED",
    "refreshUrl?": "string",
    "returnUrl?": "string"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/stripeConnections/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Commerce (Stripe); none exists for the account.

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Stripe connection id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
