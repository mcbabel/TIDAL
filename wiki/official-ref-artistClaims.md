Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A claim by an artist to own an artist profile via DSP authentication.

#### Resource `artistClaims`
| Attribute | Type | Description |
|---|---|---|
| `artistId` | string | The artist id which is being claimed |
| `externalLinks` (optional) | External_Link[] | Artist claim links external to TIDAL API |
| `provider` | string (DISTROKID, CDBABY, TUNECORE) | The DSP used for authentication |
| `recommendation` (optional) | string (CLAIM_PROFILE, CLAIM_CONTENT) | The recommended claim resolution |
| `retrievedUpcs` (optional) | LegacyBarcodeId[] | List of UPCs retrieved from the DSP |
| `status` | string (AWAITING_OAUTH, FETCHING_CONTENT, VERIFIED, NO_MATCHES, AUTHENTICATION_FAILED, PROCESSING, COMPLETED, FAILED, CANCELLED, NAME_MISMATCH, CLAIMED_ARTIST_MISMATCH) | Current status of this claim |

Relationships (`include=`): `acceptedArtists`, `owners`, `recommendedArtists`

### Get multiple artistClaims
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistClaims```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** ✅ `200` (read).

Retrieves multiple artistClaims by available filters, or without if applicable.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `filter[owners.id]` | query | yes | string[] | User id. Also accepts `me`. |
| `include` | query |  | string[] | Include related resources. Available relationships: acceptedArtists, owners, recommendedArtists |
| `includeLinkage` | query |  | string[]: acceptedArtists, owners, recommendedArtists | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: acceptedArtists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Create single artistClaim
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/artistClaims```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** not executed. Legal ownership claim for an artist profile or content. Claims are reviewed by TIDAL staff; a test claim would be a false claim.

Creates a new artistClaim.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "artistId": "string",
      "provider": "DISTROKID | CDBABY | TUNECORE"
    },
    "type": "artistClaims"
  },
  "meta": {
    "nonce?": "string",
    "redirectUrl": "string"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Delete single artistClaim
##### Method
```DELETE```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `404` `NOT_FOUND: Artist claim not found`. Not executed for real: it changes content, profiles or settings the test account does not own.

Deletes existing artistClaim.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single artistClaim
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The account has no artist claims (creating one is not done, see `POST /artistClaims`).

Retrieves single artistClaim by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: acceptedArtists, owners, recommendedArtists |
| `includeLinkage` | query |  | string[]: acceptedArtists, owners, recommendedArtists | Comma-separated direct relationships to return as linkage only, without related content. |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: acceptedArtists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update single artistClaim
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `400` `INVALID_REQUEST_BODY: Must not be null`. Not executed for real: it changes content, profiles or settings the test account does not own.

Updates existing artistClaim.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data?": {
    "attributes?": "<object>",
    "id?": "string",
    "type": "artistClaims"
  },
  "meta": {
    "authorizationCode": "string",
    "redirectUri": "string"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get acceptedArtists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}/relationships/acceptedArtists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The account has no artist claims (creating one is not done, see `POST /artistClaims`).

Retrieves acceptedArtists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: acceptedArtists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: acceptedArtists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Update acceptedArtists relationship ("to-many")
##### Method
```PATCH```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}/relationships/acceptedArtists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

**Live test 2026-11-01:** endpoint verified with a non-existent id (no change possible): `404` `NOT_FOUND: Artist claim not found`. Not executed for real: it changes content, profiles or settings the test account does not own.

Accepts one recommended artist and processes the claim, merging profile metadata or moving claimed albums according to the recommendation. Empty data cancels the claim; it does not delete any artist. Returns an acknowledgement.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": [
    {
      "id": "string",
      "type": "artists"
    }
  ],
  "meta?": {
    "mode?": "REPLACE_ALL"
  }
}
```
`?` = optional
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The account has no artist claims (creating one is not done, see `POST /artistClaims`).

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get recommendedArtists relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/artistClaims/{id}/relationships/recommendedArtists```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

**Live test 2026-11-01:** not reached. The account has no artist claims (creating one is not done, see `POST /artistClaims`).

Retrieves recommendedArtists relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | Artist claim id |
| `include` | query |  | string[] | Include related resources. Available relationships: recommendedArtists |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
| `replaceMedia` | query |  | string | Applies context-dependent replacements to media resource identifiers in selected relationships without changing stored data. Paths are comma-separated and follow `include` syntax. Example: recommendedArtists.albums |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
