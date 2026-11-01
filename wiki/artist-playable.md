#### Example Request (verified 2026-11)
* Tracks that are played when the user presses play/shuffle on the artist page.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/artist/{id}/playable?limit={limit}&offset={offset}&countryCode={country}&locale={locale}&deviceType={enum}&platform=WEB```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "play": true,
  "shuffle": true,
  "items": [
    {
      "id": 393757415,
      "title": "Consequence",
      "album": { ... },
      "artists": [ ... ],
      "duration": 313,
      ...
    }
  ],
  "url": "artist/3529689/playable",
  "cursor": null
}
```
