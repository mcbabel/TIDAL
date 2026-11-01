Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

An announced subscription price increase applicable to the user.

#### Resource `userSubscriptionPriceChanges`
| Attribute | Type | Description |
|---|---|---|
| `currency` | string | ISO 4217 currency code |
| `currentPrice` | string | Amount in the currency's major units |
| `effectiveDate` | string (date) | The date the new price takes effect |
| `newPrice` | string | Amount in the currency's major units |

Relationships (`include=`): `decision`

### Get multiple userSubscriptionPriceChanges
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userSubscriptionPriceChanges```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple userSubscriptionPriceChanges by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: decision |
| `includeLinkage` | query |  | string[]: decision | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get decision relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/userSubscriptionPriceChanges/{id}/relationships/decision```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. Only exists when TIDAL announced a price change for the subscription; none for the account.

Retrieves decision relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Price change id |
| `include` | query |  | string[] | Include related resources. Available relationships: decision |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
