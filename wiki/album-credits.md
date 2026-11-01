#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/albums/{id}/credits?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
[
  {
    "type": "Design",
    "contributors": [
      {
        "name": "David Madson"
      }
    ]
  },
  {
    "type": "Primary Artist",
    "contributors": [
      {
        "name": "The Notwist",
        "id": 3529689
      }
    ]
  },
  {
    "type": "Record Label",
    "contributors": [
      {
        "name": "Alien Transistor"
      }
    ]
  }
]
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
