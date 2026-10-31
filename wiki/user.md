#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "id": 012345678,
  "username": "test@example.com",
  "firstName": "test",
  "lastName": "example",
  "email": "test@example.com",
  "countryCode": "DE",
  "created": "2018-04-22T19:18:42.375+0000",
  "picture": "xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx",
  "newsletter": false,
  "acceptedEULA": true,
  "gender": "m",
  "dateOfBirth": "1900-02-20",
  "facebookUid": 0,
  "appleUid": null
}
```

#### Update 2026-11 (verified)
Current response fields: `id`, `username`, `profileName`, `firstName`, `lastName`, `email`, `emailVerified`, `countryCode`, `created`, `newsletter`, `acceptedEULA`, `dateOfBirth`, `facebookUid`, `appleUid`, `parentId`, `partner`, `tidalId`, `earlyAccessProgram`, `yearOfBirth`, `nostrPublicKey`, `artistId`
