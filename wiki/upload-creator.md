TIDAL Upload (independent artists upload their own music) as used by the Android app (`com.aspiro.tidal` 2.215.0).

### Get Upload Terms (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/upload/terms```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "userId": 123456789,
  "acceptedAt": null
}
```

### Accept Upload Terms (not executed)
* Accepts the upload terms in the name of the account.
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/upload/terms```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```

### Get Content Creator Info (verified 2026-11)
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{userId}/contentCreatorInfo```
##### Header
```authorization: Bearer {access_token}```
#### Example Response
``` yaml
{
  "optedInForUploader": false,
  "acceptedTerms": false
}
```

### Set Content Creator Info (not executed)
* Opts the account in to uploads and accepts the terms.
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/contentCreatorInfo```
##### Url-Encoded POST Parameter
```optedInForUploader: true|false```\
```acceptedTerms: true|false```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: application/x-www-form-urlencoded```

### Master Item (endpoint verified 2026-11 with a non-existent id: 404)
* Artist tool (`ArtistToolsService.master`) for own uploads; needs an own upload.
##### Method
```POST```
##### Url
```https://api.tidal.com/v2/tools/master/{itemId}```
##### Header
```authorization: Bearer {access_token}```\
```x-tidal-client-version: {version}```

Uploads themselves use the [Official TIDAL API](OfficialAPI) (`trackSourceFiles`, `tracks`, `albums`, `artworks`) and the storage host `https://fsu.fa.tidal.com/storage/`.
