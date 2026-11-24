# 12:12 — Para Kay Chicaaa

A mobile-friendly special-edition letter intended as **an additional page inside the existing Library ni Chico** at `https://chica.keicodes.dev/ilychicaaa`.

The page displays the **user-supplied guitar-and-vocal video** (web-compressed to approximately 18 MB) and a personal love letter. No streaming accounts, APIs, npm dependencies, external music embeds, or autoplay required. There are Google Fonts requests (with local serif/sans fallbacks).

## Integration into the existing live website (recommended)

**Do not replace the existing website or change its domain assignment.** In the GitHub repository that currently deploys `chica.keicodes.dev`, copy the contents of this package's `public/ilychicaaa/` into the existing repository's `public/ilychicaaa/` and commit. This is a standard structure for a Vite/Next/React project using a `public` folder, but the existing app/framework and existing Vercel route rules must be checked. If your project uses other static conventions, adjust accordingly.

The new page should load at `/ilychicaaa/`, including the final slash. To also support **exactly `/ilychicaaa`**, add this **rewrite** to your existing Vercel configuration, preserving all preexisting routes and rules:

```json
{ "source": "/ilychicaaa", "destination": "/ilychicaaa/index.html" }
```

If the existing website is a Next.js app and `/ilychicaaa` is served by a framework route, add it using the site's routing conventions instead of this static route. If the existing website has a catch-all SPA rewrite, ensure the specific `/ilychicaaa` rule comes first. The footer's `/` link returns to the main library.

## Preview locally

From the **`public` folder**:

```bash
python -m http.server 4173
```

Open `http://localhost:4173/ilychicaaa/`.

## Files

- `public/ilychicaaa/index.html` — responsive standalone page, CSS included.
- `public/ilychicaaa/media/para-sa-chica.mp4` — compressed version of provided recording, approximately 189 sec.
- `public/ilychicaaa/media/poster.jpg` — still frame for video preview.

## Video and copyright note

The video is the recording supplied by the user. If the performance includes a copyrighted musical composition, hosting it publicly could require permission for that composition even though the performance is your own. This package does not reproduce or quote lyrics in the page text.

## Deployment boundary

This package is prepared for integration; it is **not uploaded to GitHub or deployed to Vercel**. Existing domain and project should remain unchanged until the new route is reviewed and committed.
