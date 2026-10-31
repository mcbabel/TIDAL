#### Example Request (verified 2026-11)
* Public profile of a user.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/profiles/{userId}?countryCode={country}&locale={locale}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response

``` yaml
{
  "userId": 123456789,
  "artistId": null,
  "name": "...",
  "handle": null,
  "color": [ ... ],
  "picture": null,
  "numberOfFollowers": 0,
  "numberOfFollows": 0,
  "prompts": [ ... ],
  "socialLinks": [ ... ],
  "profileType": "..."
}
```
