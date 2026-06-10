# PlayMENA Legal

Static site hosting PlayMENA's legal pages — **Privacy Policy**, **Terms &
Conditions**, and **Data Deletion** — served via GitHub Pages. Covers our
hyper-casual mobile games (currently **Hexa Puzzle**).

## Structure

| File | Purpose |
| --- | --- |
| `index.html` | Landing page (Legal Center) linking to all documents |
| `privacy.html` | Privacy Policy |
| `terms.html` | Terms & Conditions |
| `delete-data.html` | Data deletion request page (Google Play + Facebook requirement) |
| `styles.css` | Shared styles for all pages |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (no Jekyll build) |

The current details (PlayMENA, Jordan, contact `playmena.labs@gmail.com`, min
age 13) are already filled in. Update the `Last updated` date when you change
content.

> ⚠️ These documents are a practical starting point, not legal advice. Have them
> reviewed by qualified legal counsel before relying on them.

## Live URLs (once Pages is enabled)

- Legal Center: `https://play-mena.github.io/legal/`
- Privacy Policy: `https://play-mena.github.io/legal/privacy.html`
- Terms & Conditions: `https://play-mena.github.io/legal/terms.html`
- Data Deletion: `https://play-mena.github.io/legal/delete-data.html`

## Enable GitHub Pages

1. Go to **Settings → Pages**.
2. Under **Build and deployment → Source**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then **Save**.
4. After a minute, the site is live at `https://play-mena.github.io/legal/`.

## Where to paste these URLs

| Console | Field | URL |
| --- | --- | --- |
| Google Play Console | App content → Privacy policy | `.../legal/privacy.html` |
| Google Play Console | App content → **Data deletion** | `.../legal/delete-data.html` |
| Apple App Store Connect | App Privacy → Privacy Policy URL | `.../legal/privacy.html` |
| Facebook Developer Console | App → Settings → **Data Deletion Instructions URL** | `.../legal/delete-data.html` |

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
