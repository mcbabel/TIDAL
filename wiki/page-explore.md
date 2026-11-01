#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/explore?countryCode={country}&deviceType={enums}```
##### deviceType Enums
```PHONE```\
```BROWSER```\
```DESKTOP```\
```TV```
##### Optional Url Parameter
```limit=100``` (Item Limit)\
```offset=10``` (Item Offset)
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)

#### Example Response
```yaml
{
  "selfLink": null,
  "id": "xxxxxxxxxxxx",
  "title": "Explore",
  "rows": [
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "FEATURED_PROMOTIONS",
          "width": 100,
          "title": "Featured",
          "description": "",
          "preTitle": null,
          "items": [
            {
            }
          ]
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "PAGE_LINKS_CLOUD",
          "width": 100,
          "title": "Genres",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View as list",
            "apiPath": "pages/genre_page"
          },
          "pagedList": {
            "limit": 40,
            "offset": 0,
            "totalNumberOfItems": 22,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "lines": 2
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "PAGE_LINKS_CLOUD",
          "width": 100,
          "title": "Moods, Activities & Events",
          "description": "",
          "preTitle": null,
          "showMore": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 13,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "lines": 2
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "PAGE_LINKS",
          "width": 100,
          "title": "",
          "description": "",
          "preTitle": null,
          "pagedList": {
            "limit": 6,
            "offset": 0,
            "totalNumberOfItems": 7,
            "items": [
              {
              }
            ]
          }
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "ALBUM_LIST",
          "width": 100,
          "title": "Suggested Albums for You",
          "description": "",
          "preTitle": null,
          "showMore": null,
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "listFormat": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 20,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "header": null,
          "layout": null
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "ARTIST_LIST",
          "width": 100,
          "title": "Suggested Artists for You",
          "description": "",
          "preTitle": null,
          "showMore": null,
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 10,
            "offset": 0,
            "totalNumberOfItems": 24,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "header": null,
          "layout": null
        }
      ]
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
