#### Example Request
##### Method
```POST```
##### Url
```https://api.tidal.com/v1/users/{userId}/image?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```\
```Content-Type: multipart/form-data```
##### Multipart Upload
* Upload PNG or JPG Image
#### Example Response
```yaml
{
  "picture": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
}
```