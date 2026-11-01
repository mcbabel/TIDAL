#### Example Request (verified 2026-11)
* Dominant color and BlurHash placeholder of images (covers, artist pictures). Image ids as in `cover` / `picture`.
##### Method
```GET```
##### Url
```https://api.tidal.com/v2/images/metadata-and-process?ids={imageId},{imageId}&countryCode={country}```
##### Header
```authorization: Bearer {access_token}```or\
```x-tidal-token: {client_id}``` (No Authentication Needed)\
```x-tidal-client-version: {version}```
#### Example Response
``` yaml
{
  "items": [
    {
      "resourceId": "cf203b3d-73e1-4239-98f6-49c231d8efcf",
      "selectedColor": "#4E352A",
      "blurHash": "U3Ep7?to{uvz?_xcHXmk00=c4-q^6U%e~qrE"
    }
  ]
}
```
