#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/mix?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "id": "001651ecb6f1c202a9ba7e2bbdab92"
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
