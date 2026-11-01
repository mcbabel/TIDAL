Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A user's recent search history entry.

#### Resource `searchHistoryEntries`
| Attribute | Type | Description |
|---|---|---|
| `query` | string |  |

### Delete single searchHistoryEntrie
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/searchHistoryEntries/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `search.write`, `w_usr`

**Live test 2026-11-01:** ✅ `200` (write test with cleanup).

Deletes existing searchHistoryEntrie.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Canonical opaque identifier for a user's exact saved history query. |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
