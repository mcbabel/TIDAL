Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A TIDAL Connect certificate issued for an OAuth client.

#### Resource `clientCertificates`
| Attribute | Type | Description |
|---|---|---|
| `certificateExpiresAt` (optional) | string (date-time) | Time when the issued certificate expires |
| `certificateStatus` | string (NOT_ISSUED, ACTIVE, EXPIRED, REVOKED) | Current lifecycle status of the certificate |
| `createdAt` | string (date-time) | Time when the certificate request was created |
| `lastModifiedAt` | string (date-time) | Time when the certificate request was last modified |
| `packageDownloadLink` (optional) | Link_Object | A JSON:API link object |
| `packageExpiresAt` (optional) | string (date-time) | Time until which the certificate package can be downloaded |
| `provisioningStatus` | string (PENDING, PROCESSING, OK, ERROR) | Status of certificate and package provisioning |

Relationships (`include=`): `owners`

### Create single clientCertificate
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/clientCertificates```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new clientCertificate.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "relationships": {
      "client": {
        "data": {
          "id": "string",
          "type": "clients"
        }
      }
    },
    "type": "clientCertificates"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`

### Get single clientCertificate
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/clientCertificates/{id}```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves single clientCertificate by id.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | TIDAL Connect client certificate identifier |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `includeLinkage` | query |  | string[]: owners | Comma-separated direct relationships to return as linkage only, without related content. |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`

### Get owners relationship ("to-many")
##### Method
```GET```
##### Url
```https://openapi.tidal.com/v2/clientCertificates/{id}/relationships/owners```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `r_usr`

Retrieves owners relationship.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `id` | path | yes | string | TIDAL Connect client certificate identifier |
| `include` | query |  | string[] | Include related resources. Available relationships: owners |
| `page[cursor]` | query |  | string | Server-generated cursor value pointing a certain page of items. Optional, targets first page if not specified |
##### Responses
`200` Successful response, `400`, `404`, `405`, `406`, `415`, `429`, `500`, `503`
