Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

Pricing configuration for purchasable content.

#### Resource `priceConfigurations`
| Attribute | Type | Description |
|---|---|---|
| `currency` | string (USD) | Currency code (ISO 4217) |
| `price` | string | Amount in the currency's major units |

### Get multiple priceConfigurations
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/priceConfigurations```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves multiple priceConfigurations by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[id]` | query | yes | string[] | List of price configurations IDs (e.g. `cHJpY2UtY29uZmlnLTEyMzpVUw`) |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single priceConfiguration
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/priceConfigurations```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new priceConfiguration.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "currency": "USD",
      "price": "string"
    },
    "relationships": {
      "subjects": {
        "data": [
          {
            "id": "string",
            "type": "tracks | albums"
          }
        ]
      }
    },
    "type": "priceConfigurations"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single priceConfiguration
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/priceConfigurations/{id}```
##### Access
Tier: `INTERNAL` · Auth: Client Credentials, Authorization Code + PKCE

Retrieves single priceConfiguration by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Price configuration id |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
