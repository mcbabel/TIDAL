#### Example Request (verified 2026-11)
* Adding more than one item is possible by separating the ids: ```{id},{id}```
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/favorites/artists?countryCode={country}```
##### Url-Encoded POST Parameter
```artistId: {id}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

```200 OK``` (empty body)
