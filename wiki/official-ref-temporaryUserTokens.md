Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A short-lived temporary token used to transfer user information from an authenticatedsession to another; initially for links between TIDAL web/desktop app and TIDAL'saccount pages

#### Resource `temporaryUserTokens`
| Attribute | Type | Description |
|---|---|---|

Relationships (`include=`): `owners`

### Create single temporaryUserToken
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/temporaryUserTokens```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Creates temporary login tokens for the account (new credentials).

Creates a new temporaryUserToken.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "type": "temporaryUserTokens"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single temporaryUserToken
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/temporaryUserTokens/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The account has no temporary tokens (creating one is not done, see `POST /temporaryUserTokens`).

Retrieves single temporaryUserToken by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Temporary user token id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/temporaryUserTokens/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The account has no temporary tokens (creating one is not done, see `POST /temporaryUserTokens`).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Temporary user token id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
