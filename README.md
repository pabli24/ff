# Firefox `about:config`

### Enable userChrome.css and userContent.css
`toolkit.legacyUserProfileCustomizations.stylesheets` true  

about:support → Application Basics → Profile Folder  
%APPDATA%\Mozilla\Firefox\Profiles\\<your profile\>\chrome

### Allow to install unsigned extensions
`xpinstall.signatures.required` false  

[Developer Edition](https://www.mozilla.org/firefox/developer/) and [Nightly](https://nightly.mozilla.org/) versions of Firefox allow to install unsigned add-ons

### Enable extensions on restricted domains
`extensions.webextensions.restrictedDomains` remove: ,addons.mozilla.org ,support.mozilla.org  
`privacy.resistFingerprinting.block_mozAddonManager` true  

[Enable Dark Reader on restricted pages](https://github.com/darkreader/darkreader#enable-dark-reader-on-restricted-pages-on-mozilla-firefox)

### Don’t Hide https://
`browser.urlbar.trimURLs` false

### Customize Toolbar - Density compact
`browser.compactmode.show` true

### Only the active tab have a close button
`browser.tabs.tabClipWidth` 99999

### Bigger tab width when a lot of tabs are open
`browser.tabs.tabMinWidth` 85

### Open bookmarks in new tab in background
`browser.tabs.loadBookmarksInBackground` true

### Disable Full Screen transition and “youtube.com is now full screen” warning
`full-screen-api.transition-duration.enter` 0  
`full-screen-api.transition-duration.leave` 0  
`full-screen-api.transition.timeout` 0  
`full-screen-api.warning.timeout` 0

### Font rendering like in Chromium browsers
`gfx.font_rendering.cleartype_params.rendering_mode` 5  
`gfx.font_rendering.cleartype_params.force_gdi_classic_for_families` leave empty  
`gfx.font_rendering.cleartype_params.force_gdi_classic_max_size` 0

### Pinch-To-Zoom (Alt + Scroll Wheel)
`mousewheel.with_alt.action` 5  

[Other keybinds](https://superuser.com/a/1735635)

### Disable "Menu Bar" on Alt
`ui.key.menuAccessKeyFocuses` false

### Disable Quick Find hotkey (`/` and `’` keys)
`accessibility.typeaheadfind.manual` false

### Disable Container Tabs
`privacy.userContext.enabled` false

### Disable vpn ad
`browser.vpn_promo.enabled` false

### Disable Pocket
`extensions.pocket.enabled` false

### Clear icon in the search input box (x)
`layout.forms.input-type-search.enabled` true

### DevTools - Inspect the user-agent DOM
`devtools.inspector.showAllAnonymousContent` true

### DevTools - Disable paused state overlay
`devtools.debugger.features.overlay` false

### URL bar calculator
`browser.urlbar.suggest.calculator`	true

### Disable Windows 10/11 efficiency mode
`dom.ipc.processPriorityManager.backgroundUsesEcoQoS` false

### Fix Twitch player freeze while playing games on the 2nd monitor
`gfx.webrender.compositor` false

### HEVC (H.265) Codec Support
`media.wmf.hevc.enabled` 1  

Windows 10/11:
- Paid - [HEVC Video Extensions](https://apps.microsoft.com/detail/9nmzlz57r3t7)
- Free - [HEVC Video Extensions from Device Manufacturer](https://www.codecguide.com/media_foundation_codecs.htm)
<!--
### Other
`media.navigator.video.default_fps` 60
`media.navigator.mediadatadecoder_vpx_enabled` true
-->
# Useful links
https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Experimental_features

https://searchfox.org/mozilla-release/source/modules/libpref/init/StaticPrefList.yaml  
https://searchfox.org/mozilla-release/source/browser/app/profile/firefox.js  
https://searchfox.org/mozilla-release/source/modules/libpref/init/all.js  

`about:support`  
`about:about`

# Debugger
Devtools → Debugger → Breakpoints → Pause on debugger statement

Bookmarklet:
```javascript
javascript:(() => { setTimeout(() => {debugger}, 3000) })();
```
