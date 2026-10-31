#### Example Request (verified 2026-11)
* Credits grouped by role. Same format as [Get Album Credits](album-credits).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/credits?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
[
  {
    "type": "Composer",
    "contributors": [
      {
        "name": "Markus Acher",
        "id": 10371697
      },
      {
        "name": "Michael Acher"
      }
    ]
  },
  {
    "type": "Music Publisher",
    "contributors": [
      {
        "name": "Abzocker Musikverlag"
      }
    ]
  }
]
```
