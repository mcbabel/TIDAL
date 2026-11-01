Generated from the official OpenAPI spec `1.10.218` (2026-11-01). Base url: ```https://openapi.tidal.com/v2```. Back to [Official API Endpoints](official-endpoints).

A manual artist claim submitted with identity verification details.

#### Resource `manualArtistClaims`
| Attribute | Type | Description |
|---|---|---|
| `acceptedTerms` (optional) | boolean | Accepted terms and conditions |
| `artistId` | string | Artist ID being claimed |
| `createdAt` (optional) | string (date-time) | Timestamp when the claim was created |
| `distributorName` (optional) | string | Distributor name |
| `enrollmentType` (optional) | string | Enrollment type |
| `errorReason` (optional) | string | Error reason if claim failed |
| `labelContactEmail` (optional) | string | Label contact email |
| `labelContactName` (optional) | string | Label contact name |
| `labelName` (optional) | string | Label name |
| `lastModifiedAt` (optional) | string (date-time) | Timestamp when the claim was last modified |
| `legalFirstName` | string | Legal first name |
| `legalLastName` | string | Legal last name |
| `managerEmail` (optional) | string | Manager email |
| `managerName` (optional) | string | Manager name |
| `role` (optional) | string | Role |
| `selectedAlbums` (optional) | string[] | Album IDs selected by user |
| `selectedSingles` (optional) | string[] | Single IDs selected by user |
| `socialLink` (optional) | Link_Object | A JSON:API link object |
| `status` (optional) | string (SUBMITTED, PENDING, APPROVED, REJECTED) | Claim status |
| `upcs` (optional) | string[] | UPCs associated with the claim |
| `websiteOrSocialLink` | Link_Object | A JSON:API link object |

### Create single manualArtistClaim
##### Method
```POST```
##### Url
```https://openapi.tidal.com/v2/manualArtistClaims```
##### Access
Tier: `INTERNAL` · Auth: Authorization Code + PKCE · Scopes: `w_usr`

Creates a new manualArtistClaim.
##### Parameters
| Name | In | Required | Type | Description |
|---|---|---|---|---|
| `Idempotency-Key` | header |  | string | Unique idempotency key for safe retry of mutation requests. If the same caller repeats a key with the same method, path, query and payload, the original response is replayed. If the request differs, a 422 error is returned. |
##### Body (`application/vnd.api+json`)
``` yaml
{
  "data": {
    "attributes": {
      "acceptedTerms?": "boolean",
      "artistId": "string",
      "distributorName?": "string",
      "errorReason?": "string",
      "labelContactEmail?": "string",
      "labelContactName?": "string",
      "labelName?": "string",
      "legalFirstName": "string",
      "legalLastName": "string",
      "managerEmail?": "string",
      "managerName?": "string",
      "role?": "string",
      "selectedAlbums?": [
        "string"
      ],
      "selectedSingles?": [
        "string"
      ],
      "socialLink?": {
        "href": "string (uri)"
      },
      "upcs?": [
        "string"
      ],
      "websiteOrSocialLink": {
        "href": "string (uri)"
      }
    },
    "type": "manualArtistClaims"
  }
}
```
`?` = optional
##### Responses
`201` Successful response, `400`, `404`, `405`, `406`, `409`, `415`, `422`, `429`, `500`, `503`
