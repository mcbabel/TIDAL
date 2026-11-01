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

#### Update 2026-11 (not executed)
Not tested: it replaces the profile picture of the account. There is no documented way to restore the previous picture (or to remove the picture again), so the test could not be undone.
