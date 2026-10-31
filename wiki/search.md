#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/search?countryCode={country}&query={query}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "artists": {
    "limit": 10,
    "offset": 0,
    "totalNumberOfItems": 1,
    "items": [
      {
        "id": 3529689,
        "name": "The Notwist",
        "artistTypes": [
          "ARTIST",
          "CONTRIBUTOR"
        ],
        "url": "http://www.tidal.com/artist/3529689",
        "picture": "2a4abc4a-faf5-4c06-b2a4-bf142459d894",
        "popularity": 35,
        "artistRoles": [
          {
            "categoryId": -1,
            "category": "Artist"
          },
          {
            "categoryId": 11,
            "category": "Performer"
          },
          {
            "categoryId": 1,
            "category": "Producer"
          },
          {
            "categoryId": 2,
            "category": "Songwriter"
          },
          {
            "categoryId": 3,
            "category": "Engineer"
          }
        ],
        "mixes": {
          "MASTER_ARTIST_MIX": "0157026712a3687e12af164ecb10ce",
          "ARTIST_MIX": "00008ded8a6682c338c2fbabd6619f"
        }
      }
    ]
  },
  "albums": {
    "limit": 10,
    "offset": 0,
    "totalNumberOfItems": 17,
    "items": [
      {
      }
    ]
  },
  "playlists": {
    "limit": 10,
    "offset": 0,
    "totalNumberOfItems": 2,
    "items": [
      {
      }
    ]
  },
  "videos": {
    "limit": 10,
    "offset": 0,
    "totalNumberOfItems": 0,
    "items": []
  },
  "topHit": {
    "value": {
      "id": 3529689,
      "name": "The Notwist",
      "artistTypes": [
        "ARTIST",
        "CONTRIBUTOR"
      ],
      "url": "http://www.tidal.com/artist/3529689",
      "picture": "2a4abc4a-faf5-4c06-b2a4-bf142459d894",
      "popularity": 35,
      "artistRoles": [
        {
          "categoryId": -1,
          "category": "Artist"
        },
        {
          "categoryId": 11,
          "category": "Performer"
        },
        {
          "categoryId": 1,
          "category": "Producer"
        },
        {
          "categoryId": 2,
          "category": "Songwriter"
        },
        {
          "categoryId": 3,
          "category": "Engineer"
        }
      ],
      "mixes": {
        "MASTER_ARTIST_MIX": "0157026712a3687e12af164ecb10ce",
        "ARTIST_MIX": "00008ded8a6682c338c2fbabd6619f"
      }
    },
    "type": "ARTISTS"
  }
}
```

#### Update 2026-11 (verified)
* Still works with `x-tidal-token`. Optional: `types=ARTISTS,ALBUMS,TRACKS,VIDEOS,PLAYLISTS`, `limit`, `offset`.
* The response additionally contains `topHit`: `{"value": {...}, "type": "ARTISTS"}`.
* The TIDAL apps now use [Search v2](search-v2).
