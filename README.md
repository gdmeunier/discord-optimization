# Discord Optimization

Optimize Discord's Web client on low-end devices by blocking all unnecessary API calls and assets downloading.

This repository currently covers **Chromium**-based Web browsers only (*Chrome*, *Chromium*, *Supermium*, *Brave Browser* [...]), because I don't use Firefox-based ones so I can't test on them.

However the CSS rules and URL patterns should be able to be used in a Firefox-based Web browser too, as long as you find suitable alternative extensions for Firefix-based browsers.

## Required Chrome extensions

<table>
  <tr>
    <td><b>uBlock Origin</b></td><td><a href="https://github.com/gorhill/ublock">https://github.com/gorhill/ublock</a></td>
  </tr>
  <tr>
    <td><b>HTTP Request Blocker</b></td><td><a href="https://github.com/clupasq/ChromeHttpRequestBlocker">https://github.com/clupasq/ChromeHttpRequestBlocker</a></td>
  </tr>
</table>

# Optimize Discord with uBlock Origin

Add the below filter lines to your list of custom filters in the uBlock Origin extension settings:

```
! -------------------------
! ----- Discord START -----
! -------------------------

! No login page background picture
discord.com##div[class^="app"] > div[class^="characterBackground"] > div[class^="artwork"]

! No QR code login
discord.com##[class^="qrCodeContainer"]
discord.com##div[class^="qrLoginInner"] > h2[class^="heading"]
discord.com##div[class^="qrLoginInner"] > div[class^="text-md"]

! Avatar missing Nitro picture frame placeholder removal
discord.com##div[class^="avatar"] > div[class^="wrapper"] > svg[class^="avatarDecorationContainer"]

! Avatar missing Nitro nameplate placeholder removal
discord.com##div[role="listitem"] > div[class*="nameplated"] > div[class^="container"]

! -----------------------
! ----- Discord END -----
! -----------------------
```

# Optimize Discord with HTTP Request Blocker

Add the below filter lines to your list of blocked URL patterns in the HTTP Request Blocker extension settings:

<table>
  <tr>
    <td>*://discord.com/api/v*/channels/*/typing</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/saved-messages</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/guilds/*/top-emojis</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/dd05fd1ea37e7747.png</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/experiments*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/apex/experiments*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/promotions*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/auth/location-metadata</td>
  </tr>
  <tr>
    <td>*://discord.com/error-reporting-proxy/*</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/sentry.*.js</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.mp3</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.mp4</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.webm</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/assets/collectibles/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/collectibles-products/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/collectibles-*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/collectibles*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/survey*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/referrals*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/entitlements*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/virtual-currency*</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/version.*.json*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/changelogs/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/store/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/wishlist*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/games/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/games*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/quests/*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/bad-domains/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/content-inventory/users/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/stickers/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/widgets/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/widget-configs/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/applications/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/billing/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/settings-proto/*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/avatar-decoration-presets/*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/assets/content/*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/banners/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/*/application-identities*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/partner-sdk/*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/detectables/*</td>
  </tr>
  <tr>
    <td>*://*.discordapp.com/media/v*/collectibles-shop/*</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.woff2</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.woff</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.otf</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.ttf</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/*.eot*</td>
  </tr>
  <tr>
    <td>*://discord.com/assets/d8680b1c1576ecc8.svg</td>
  </tr>
  <tr>
    <td>*://status.discord.com/api/v*/scheduled-maintenances*</td>
  </tr>
  <tr>
    <td>*://status.discord.com/api/v*/incidents*</td>
  </tr>
  <tr>
    <td>*://*.ingest.sentry.io/*</td>
  </tr>
  <tr>
    <td>*://a.nel.cloudflare.com/report/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/users/@me/application-command-index</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/application-directory-static/collections*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/applications-with-assets*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/activities/shelf</td>
  </tr>
  <tr>
    <td>*://cdn.discordapp.com/app-icons/*</td>
  </tr>
  <tr>
    <td>*://cdn.discordapp.com/app-assets/*/store/*</td>
  </tr>
  <tr>
    <td>*://discord.com/api/v*/gifs/trending*</td>
  </tr>
</table>

# Done!

Now your Discord Web client will be much faster on your low-end devices.


