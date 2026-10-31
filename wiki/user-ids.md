#### Example Request
##### Method
```GET```
##### Url
```https://api.tidal.com/v1/users/{id}/favorites/ids?countryCode={country}```
##### Header
```authorization: Bearer {access_token}```
#### Example Response

``` yaml
{
  "VIDEO": [
  ],
  "ARTIST": [
    "3529689",
    "3840013",
  ],
  "ALBUM": [
    "103608996",
    "103687796",
    "122122018",
  ],
  "TRACK": [
    "11331196",
    "13758717",
    "16024895",
    "17078591",
    "18681940",
    "36534565",
    "36534567",
    "422704",
    "45111353",
    "6756308",
    "6756840",
    "6757154",
    "73215316",
    "73215326"
  ],
  "PLAYLIST": [
    "xxxxxxx-xxxx-xxxx-xxxx-00fde2d67f4f"
  ]
}
```