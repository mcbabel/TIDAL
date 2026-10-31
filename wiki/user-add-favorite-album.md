#### Example Request (verified 2026-11)
* Adding more than one item is possible by separating the ids: ```{id},{id}```
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/favorites/albums?countryCode={country}```
##### Url-Encoded POST Parameter
```albumId: {id}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

```200 OK``` (empty body)
