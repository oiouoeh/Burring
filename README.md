# Burring Calculator - GitHub Pages install guide (v1.5)

Upload **every** file in this folder to the ROOT of a GitHub repository. The app then installs on a phone and runs without internet.

## Files
index.html (the app, must keep this name) | sw.js (offline saving) | manifest.webmanifest | icon-*.png | .nojekyll (hidden file)

## Upload
1. GitHub -> **+ -> New repository** (free accounts need **Public** for Pages)
2. **Add file -> Upload files** -> drop all files -> **Commit changes**
3. **Settings -> Pages -> Deploy from a branch -> main / (root) -> Save**
4. After 1-2 minutes: `https://<user>.github.io/<repo>/` (repo name is case-sensitive)

## Install on the phone
1. Open the address **while online**. Wait until the small dot at the bottom left is **green** and "Ready for offline use" appears (orange = still saving, stay online).
2. Browser menu -> **Add page to -> Install web app** / **Install app** (may take a few seconds to appear).
3. Open the installed icon, then open it again in airplane mode to confirm.

## New version
Overwrite `index.html`, then change the version name in **both** `sw.js` (`const CACHE = PREFIX + 'v1.5'`) and `index.html` (`var APP_CACHE = 'burr-v1.5'`), upload both, close and reopen the app.

## Several apps on one github.io address
They share ONE Cache Storage. Give each app a unique prefix (this one: `burr-`) and only ever delete caches with your own prefix.

## Notes
Strategy: network-first. External (CDN) files do not work offline - embed them. Page size: about 0.0 MB.
