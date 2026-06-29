# PlayMENA Legal & Developer Site

Static site for PlayMENA, served via GitHub Pages from the organization root
(`play-mena.github.io`). Hosts our legal pages — **Privacy Policy**, **Terms &
Conditions**, **Data Deletion** — and the **app-ads.txt** file for AdMob.
Covers our hyper-casual mobile games (currently **Hexa Puzzle**).

> **Repo name matters:** this repo must be named **`play-mena.github.io`** so the
> site serves at the domain root. That root is required for `app-ads.txt` to be
> found, and gives the legal pages clean URLs.

## Structure

| File | Purpose |
| --- | --- |
| `index.html` | Landing page (Legal Center) linking to all documents |
| `privacy.html` | Privacy Policy |
| `terms.html` | Terms & Conditions |
| `delete-data.html` | Data deletion request page (Google Play + Facebook requirement) |
| `app-ads.txt` | AdMob authorized-sellers file (must sit at the domain root) |
| `styles.css` | Shared styles for all pages |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (no Jekyll build) |

Details (PlayMENA, Jordan, contact `playmena.labs@gmail.com`, min age 13) are
already filled in. Update the `Last updated` date when you change content.

> ⚠️ The legal documents are a practical starting point, not legal advice. Have
> them reviewed by qualified legal counsel before relying on them.

## Live URLs (once Pages is enabled)

- Legal Center: `https://play-mena.github.io/`
- Privacy Policy: `https://play-mena.github.io/privacy.html`
- Terms & Conditions: `https://play-mena.github.io/terms.html`
- Data Deletion: `https://play-mena.github.io/delete-data.html`
- app-ads.txt: `https://play-mena.github.io/app-ads.txt`

## Enable GitHub Pages

1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then **Save**.
4. After a minute, the site is live at `https://play-mena.github.io/`.

## app-ads.txt (AdMob)

`app-ads.txt` authorizes who may sell your ad inventory and must live at the
**root** of the developer website listed on your store pages.

1. The file already contains your AdMob line:
   `google.com, pub-9780554709620172, DIRECT, f08c47fec0942fa0`
   (add a new line for each additional ad network you integrate).
2. In **Google Play Console** and **App Store Connect**, set the app's
   **website / developer URL** to `https://play-mena.github.io` so AdMob checks
   the right domain.
3. Verify it loads at `https://play-mena.github.io/app-ads.txt`.
4. Wait up to ~24 hours, then check status in **AdMob → app-ads.txt**.

## Where to paste these URLs

| Console | Field | URL |
| --- | --- | --- |
| Google Play Console | App content → Privacy policy | `https://play-mena.github.io/privacy.html` |
| Google Play Console | App content → **Data deletion** | `https://play-mena.github.io/delete-data.html` |
| Google Play Console | Store listing → **Website** | `https://play-mena.github.io` |
| Apple App Store Connect | App Privacy → Privacy Policy URL | `https://play-mena.github.io/privacy.html` |
| Facebook Developer Console | App → Settings → **Data Deletion Instructions URL** | `https://play-mena.github.io/delete-data.html` |
| AdMob | app-ads.txt (root of developer site) | `https://play-mena.github.io/app-ads.txt` |

## Google Play "Data Safety" cheat-sheet

Fill the Data Safety form (Play Console → App content → Data safety) to match
the privacy policy. For our current flow:

| Data type | Collected? | Shared? | Notes |
| --- | --- | --- | --- |
| Name | Yes — **optional** | No | Only if the player signs in with Facebook/Apple/Google |
| Email address | No | — | We never receive the social-login email/password |
| User IDs | Yes | Yes | PlayFab player ID, social account ID |
| Purchase history | Yes | No | In-app purchases via Google Play / Apple |
| App interactions / in-app actions | Yes | No | Gameplay, levels, scores (Firebase) |
| Crash logs | Yes | No | Firebase Crashlytics |
| Diagnostics / performance | Yes | No | Firebase Analytics |
| Device or other IDs (Advertising ID) | Yes | Yes | Google AdMob (ads), Firebase |
| Approximate location | Yes | Yes | Coarse, inferred from IP by ad/analytics partners |
| Precise location | No | — | Not collected |

Also declare:

- **Data is encrypted in transit:** Yes.
- **Users can request deletion:** Yes → `delete-data.html`.
- **Purpose** for the above: App functionality, Analytics, Advertising, and
  (for purchases) handling payments.
- If you target children, complete the **Designed for Families** section, use
  certified ad SDKs, and serve **non-personalized ads** to under-13 users in
  AdMob.

> Keep this table and the privacy policy in sync whenever you add an SDK or a new
> data flow — mismatches are the most common cause of Play review rejections.

## Local preview

Open `index.html` directly in a browser, or run a local server:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```
