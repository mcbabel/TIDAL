#### Example Request (verified 2026-11)
* Tracks of the artist radio. Same item format as [Get Track](track).
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/artists/{id}/radio?countryCode={country}```
##### Optional Url Parameter
```limit=10``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 2,
  "offset": 0,
  "totalNumberOfItems": 100,
  "items": [
    {
      "id": 38519997,
      "title": "Object 3",
      ...
    }
  ]
}
```
