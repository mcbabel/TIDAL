#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/pages/videos?countryCode={country}&deviceType={enums}```
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
  "title": "Videos",
  "rows": [
    {
      "modules": [
        {
          "id": "xxxxxxxxxxxx",
          "type": "MULTIPLE_TOP_PROMOTIONS",
          "width": 100,
          "title": "Featured",
          "description": "",
          "preTitle": null,
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
          "title": "Album Experiences",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/25/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "listFormat": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 39,
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
          "title": "TIDAL Originals",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 100,
            "offset": 0,
            "totalNumberOfItems": 10,
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
          "type": "VIDEO_LIST",
          "width": 100,
          "title": "New Music Videos",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/25/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "listFormat": null,
          "scroll": "HORIZONTAL",
          "layout": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 445,
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
          "type": "PLAYLIST_LIST",
          "width": 100,
          "title": "Artist Video Essentials",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/25/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 82,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/4a254dd6-506c-49d7-b95b-a0aa58e8fcc8"
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
          "type": "PLAYLIST_LIST",
          "width": 100,
          "title": "Shows",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "scroll": "HORIZONTAL",
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 44,
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
          "type": "VIDEO_LIST",
          "width": 100,
          "title": "Movies",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "listFormat": null,
          "scroll": "HORIZONTAL",
          "layout": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 27,
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
          "type": "VIDEO_LIST",
          "width": 100,
          "title": "Visual Albums",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/2"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "listFormat": null,
          "scroll": "HORIZONTAL",
          "layout": null,
          "pagedList": {
            "limit": 15,
            "offset": 0,
            "totalNumberOfItems": 11,
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
          "type": "VIDEO_LIST",
          "width": 100,
          "title": "Performances",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "listFormat": null,
          "scroll": "HORIZONTAL",
          "layout": null,
          "pagedList": {
            "limit": 40,
            "offset": 0,
            "totalNumberOfItems": 69,
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
          "type": "VIDEO_LIST",
          "width": 100,
          "title": "Conversations",
          "description": "",
          "preTitle": null,
          "showMore": {
            "title": "View all",
            "apiPath": "pages/single-module-page/xxxxxxxxxxxx/1"
          },
          "supportsPaging": false,
          "quickPlay": false,
          "listFormat": null,
          "scroll": "HORIZONTAL",
          "layout": null,
          "pagedList": {
            "limit": 40,
            "offset": 0,
            "totalNumberOfItems": 41,
            "items": [
              {
              }
            ],
            "dataApiPath": "pages/data/xxxxxxxxxxxx"
          },
          "showTableHeaders": false
        }
      ]
    }
  ]
}
```

#### Update 2026-11 (verified)
Still works (`200`), response format as above.
