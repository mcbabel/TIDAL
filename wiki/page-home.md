#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/home?countryCode={country}&deviceType={enums}```
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
  "title": "Home",
  "rows": [
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "MULTIPLE_TOP_PROMOTIONS",
          "width": 100,
          "title": "",
          "description": "",
          "preTitle": null,
          "items": [
            {
            }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "showTableHeaders": true
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "ALBUM_LIST",
          "width": 100,
          "title": "Suggested New Albums",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/3/xxxxxxxxxxxx/1"
          },
          "supportsPaging": true,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "listFormat": null,
          "pagedList": {
            "limit": 20,
            "offset": 0,
            "totalNumberOfItems": 74,
            "items": [
              {
              }
          }
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "PLAYLIST_LIST",
          "width": 100,
          "title": "The Charts",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/3/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 20,
            "offset": 0,
            "totalNumberOfItems": 23,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "layout": null,
          "playlistStyle": null
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "ALBUM_LIST",
          "width": 100,
          "title": "Popular Albums",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/3/xxxxxxxxxxxx/4"
          },
          "supportsPaging": true,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "listFormat": null,
          "pagedList": {
            "limit": 20,
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
          "type": "PLAYLIST_LIST",
          "width": 100,
          "title": "Party",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/3/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 16,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "showTableHeaders": false
        }
      ]
    },
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "ALBUM_LIST",
          "width": 100,
          "title": "Staff Picks: Albums",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/3/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "listFormat": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 344,
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
          "id": "xxxxxxxxxxxxxxxxxxxxxxxxx",
          "type": "PLAYLIST_LIST",
          "width": 100,
          "title": "Podcasts",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/3/xxx/1"
          },
          "supportsPaging": true,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 20,
            "offset": 0,
            "totalNumberOfItems": 23,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "layout": null,
          "playlistStyle": null
        }
      ]
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
