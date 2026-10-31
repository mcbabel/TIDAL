#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/search/playlists?countryCode={country}&query={query}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "limit": 1,
  "offset": 0,
  "totalNumberOfItems": 16,
  "items": [
    {
      "uuid": "6b314331-482c-4c15-8a5b-ee6cd056eb1e",
      "title": "Now Playing: GoGo Penguin",
      "numberOfTracks": 14,
      "numberOfVideos": 0,
      "creator": {
        "id": 4764457,
        "name": "GoGo Penguin",
        "type": null
      },
      "description": "\"Just some of the music we’ve been listening to while prepping for and recording our new album.\" - GoGo Penguin",
      "duration": 3560,
      "lastUpdated": "2020-03-25T10:33:54.000+0000",
      "created": "2019-12-05T12:42:32.000+0000",
      "type": "ARTIST",
      "publicPlaylist": true,
      "url": "http://www.tidal.com/playlist/6b314331-482c-4c15-8a5b-ee6cd056eb1e",
      "image": "4c039ebd-07e5-4852-9444-32f0d4bfe898",
      "popularity": 1,
      "squareImage": "a8888a46-29c7-4522-a389-c4c58f045af0",
      "promotedArtists": [
        {
          "id": 5165814,
          "name": "D.D Dumbo",
          "type": "MAIN"
        },
        {
          "id": 2520,
          "name": "Gil Scott-Heron",
          "type": "MAIN"
        },
        {
          "id": 4000027,
          "name": "Jamie xx",
          "type": "MAIN"
        },
        {
          "id": 4811562,
          "name": "Hiatus Kaiyote",
          "type": "MAIN"
        }
      ],
      "lastItemAddedAt": null
    }
  ]
}
```