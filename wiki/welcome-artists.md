### Get Artist Categories (verified 2026-11)
* Artist picker shown to new users ("pick your favorite artists").
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/welcome/categories/artists?limit=12&countryCode={country}&locale={locale}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
[
  {
    "category": {
      "id": 9066,
      "name": "..."
    },
    "pagedList": {
      "limit": 12,
      "offset": 0,
      "totalNumberOfItems": 12,
      "items": [
        {
          "id": 0,
          "name": "...",
          "url": "http://www.tidal.com/artist/...",
          "picture": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
        }
      ]
    },
    "position": 1,
    "width": 100,
    "type": "ARTIST_CATEGORY",
    "scroll": "HORIZONTAL"
  }
]
```

### Get More Artists Of A Category (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/welcome/categories/{categoryId}/artists?limit=6&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```

### Get Similar Artists (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/welcome/artists/{artistId}/similar?limit=5&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "items": [
    {
      "id": 0,
      "name": "...",
      "url": "http://www.tidal.com/artist/...",
      "picture": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
    }
  ]
}
```

### Save Selected Artists (from web player code 2026-11, not executed)
* Stores the picked artists for personal recommendations.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/welcome/users/artists?countryCode={country}```
##### Url-Encoded POST Parameter
```artistIds: {id},{id},{id}```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

#### Update 2026-11: Test status
`Save Selected Artists` was not executed: it overwrites the artist selection that TIDAL uses for recommendations, and the previous selection cannot be read back to restore it. All `GET` endpoints of this page are verified.
