#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/tracks/{id}/contributors?countryCode={country}```
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
  "totalNumberOfItems": 0,
  "items": [
    {
      "name": "Acher Markus",
      "role": "Composer"
    },
    {
      "name": "Acher Michael",
      "role": "Composer"
    },
    {
      "name": "Abzocker Musikverlag",
      "role": "Music Publisher"
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
