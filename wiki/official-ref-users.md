Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A TIDAL user account.

#### Resource `users`
| Attribute | Type | Description |
|---|---|---|
| `country` | string | ISO 3166-1 alpha-2 country code |
| `developerAccessTier` | string (THIRD_PARTY, THIRD_PARTY_PROD, PARTNER, PARTNER_TIDAL_CONNECT, INTERNAL) | Developer access tier for this user. |
| `email` (optional) | string | email address |
| `emailVerified` (optional) | boolean | Is the email verified |
| `firstName` (optional) | string | Users first name |
| `lastName` (optional) | string | Users last name |
| `nostrPublicKey` (optional) | string | Users nostr public key |
| `username` | string | user name |

Relationships (`include=`): `artist`

### Get single user
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/users/{id}```
##### Access
Tier: `THIRD_PARTY` · Auth: Authorization Code + PKCE · Scopes: `r_usr`, `user.read`

Retrieves single user by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: artist |
| `includeLinkage` | query |  | string[]: artist | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get artist relationship ("to-one")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/users/{id}/relationships/artist```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE

Retrieves artist relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | User id. Use `me` for the authenticated user's resource |
| `include` | query |  | string[] | Include related resources. Available relationships: artist |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: artist.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
