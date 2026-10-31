
***
#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/playlists/{uuid}?countryCode={country}```
##### Header
```authorization: Bearer {access_token}``` or\
```x-tidal-token: {client_id}``` (No Authentication Needed)
#### Example Response

``` yaml
{
  "uuid": "854e65fb-857a-4db3-9108-4be406e8ea3d",
  "title": "GoGo Penguin: At Home",
  "numberOfTracks": 17,
  "numberOfVideos": 0,
  "creator": {
    "id": 4764457,
    "name": "GoGo Penguin",
    "type": null
  },
  "description": "\"As a teenager, my mates and I would make compilations for each other. Even as kids we knew how powerful music can be in sharing feelings and ideas,” recalls Chris Illingworth, pianist for the exploratory jazz trio GoGo Penguin. “It’s a crazy and difficult time right now; there’s a lot of fear, worry and anxiety going ’round. So when Nick [Blacka], Rob [Turner] and I decided to put this playlist together, we looked for tracks that make us feel good and raise our spirits. Hopefully this playlist can bring a bit of happiness, enjoyment and togetherness in these strange and difficult days. We might need to keep our distance from each other, but it’s as important as ever to look out for each other. Stay safe and much love.” (Photo: Jon Shard)",
  "duration": 4579,
  "lastUpdated": "2020-04-14T15:12:51.137+0000",
  "created": "2020-04-10T09:06:08.403+0000",
  "type": "ARTIST",
  "publicPlaylist": true,
  "url": "http://www.tidal.com/playlist/854e65fb-857a-4db3-9108-4be406e8ea3d",
  "image": "b5dc1788-a989-48b7-830d-380ae1f89729",
  "popularity": 0,
  "squareImage": "3d44aa40-5ffb-420b-854f-7b387ce59f84",
  "promotedArtists": [
    {
      "id": 4764457,
      "name": "GoGo Penguin",
      "type": "MAIN"
    },
    {
      "id": 3526620,
      "name": "The Daktaris",
      "type": "MAIN"
    },
    {
      "id": 4811562,
      "name": "Hiatus Kaiyote",
      "type": "MAIN"
    },
    {
      "id": 3508438,
      "name": "Airto Moreira",
      "type": "MAIN"
    }
  ],
  "lastItemAddedAt": "2020-04-13T21:38:32.668+0000"
}
```

#### Update 2026-11 (verified)
New fields in the response: `customImageUrl`, `promotedArtists` (list of artists with `id`, `name`, `handle`, `type`, `picture`) and `lastItemAddedAt`.
