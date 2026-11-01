#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/videos/{id}/contributors?countryCode={country}```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 10,
  "offset": 0,
  "totalNumberOfItems": 8,
  "items": [
    {
      "name": "Rob Turner",
      "role": "Composer"
    },
    {
      "name": "Chris Illingworth",
      "role": "Composer"
    },
    {
      "name": "Nick Blacka",
      "role": "Composer"
    },
    {
      "name": "Dan Parrott",
      "role": "Film Director"
    },
    {
      "name": "Kerstan Makness",
      "role": "Film Producer"
    },
    {
      "name": "BMG Rights Management (UK) Ltd.",
      "role": "Music Publisher"
    },
    {
      "name": "Dan Parrott",
      "role": "Video Director"
    },
    {
      "name": "Kerstan Makness",
      "role": "Video Producer"
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
