#### Example Request (verified 2026-11)
* Country of the caller (by IP).
* Variant used by the web player: `GET https://api.tidal.com/v1/country/context?countryCode=WW&locale={locale}&deviceType=BROWSER`
* Health check: `GET https://api.tidal.com/v1/ping` → `OK`
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/country```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "countryCode": "DE"
}
```
