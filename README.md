<p align="center">
  TIDAL API documentation.
</p>

<p align="center">
  <a href="https://ko-fi.com/H2H12FS8P" alt="kofi">
    <img src="https://www.ko-fi.com/img/githubbutton_sm.svg">
  </a>
</p>

#### Background
The TIDAL API is not public and thus no documentation exists. I've decompiled various TIDAL App Versions and debundled the Browser JS App to gain some knowledge about the endpoints, general API functions and the authflow. This is the documentation repository.\
[Wiki (Work in Progress)](https://github.com/openTIDAL/docTIDAL/wiki) \
The wiki pages are also part of this repository in the [wiki](wiki) folder ([Start](wiki/Home.md)). \
I reversed engineered the TIDAL device authorization grant (RFC 8628) since the web flow (RFC 6749) is reCaptcha v3 secured. 

#### Support
I spend dozens of hours in reverse engineering and writing a C Library (not released yet). If you like what I do you can buy me a coffee.

#### Disclaimer
I deeply discourage you from building and distributing copyright-infringing apps. Create something that adds up to TIDALs Service and improves it.

#### Changelog

11-01-2026 (Android):
  - Complete documentation of the TIDAL Android app API (2.215.0): overview, all 271 private endpoints with live test status, new pages for Android-only features (wiki/Android.md, wiki/android-endpoints.md)

11-01-2026 (live tested):
  - Every endpoint was tested live with a real account (write tests with cleanup); results and reasons for the few untested ones in the Test Report (wiki/TestReport.md)

11-01-2026 (complete coverage):
  - Every API call of the TIDAL web player is documented (blocks, onboarding, cloud queue, DRM, streaming privileges, marketplace, suggestions, ...)
  - Full reference of the official API: all 438 operations on 89 resource pages
  - Status page for the remaining legacy endpoints

11-01-2026:
  - Documentation updated to the current TIDAL API and verified against the live API (see [wiki/Changelog.md](wiki/Changelog.md))
  - Created Entries: Audio Quality (MQA removed, HI_RES_LOSSLESS), Track PlaybackInfo, Authorization Code + PKCE, Client Credentials, Session, v2 Home Feed, v2 Artist Page, v2 Search, My Collection Folders, Playlist Visibility and many more
  - Created Section: Official TIDAL API (openapi.tidal.com/v2) with endpoint list and Migration Guide

12-25-2020:
  - Created Entries: Get Favorite Mixes, Add Favorite Mixes, Delete Favorite Mixes (Thank you @AustinJ235)

11-14-2020:
  - Created Entry: Activity Feed 
  - Created Entry: Second API
  - Created Entry: Logout Endpoint
