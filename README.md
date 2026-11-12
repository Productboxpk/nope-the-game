# Nope

A ~~rage~~ calm, peaceful platformer. Very relaxing. Trust me.

Created by Engineers with ♥ at [Productbox](https://productbox.dev).

## What's in here

```
public/index.html   the whole game (HTML + CSS + JS, no dependencies)
render.yaml         Render Blueprint: deploys public/ as a static site
```

## Run it locally

Open `public/index.html` in a browser. That's it.

## Deploy to Render

1. Push this folder to a GitHub (or GitLab) repo.
2. In Render: **New → Blueprint**, connect the repo, and apply.
   (Or **New → Static Site**, pick the repo, leave the build command empty-ish
   (`echo ok`), and set the publish directory to `public`.)
3. Render gives you a `https://nope-xxxx.onrender.com` address.
4. Optional custom domain: in the service's **Settings → Custom Domains**, add
   `nope.productbox.dev`, then add the CNAME record Render shows you at your DNS provider.

Every push to the main branch redeploys automatically.

## Testing tips

- Start on a specific level: add `#level-5` to the URL (1–9).
  Runs started this way are practice runs and don't go on the Deathboard.
- The Deathboard currently lives in each browser (localStorage). A shared,
  online Deathboard needs an API — see "Next steps".

## Next steps (not done yet)

- **Shared Deathboard + "who played" data:** a small API (e.g. a Render web service
  with Postgres, or Supabase) with `POST /runs` and `GET /deathboard`. The game's
  `save()` and `openBoard()` functions are the two places to wire it in.
- **Notifications:** have the API post to a Slack channel or send an email when
  someone starts or finishes. Keep webhook URLs and keys in the API, never in the page.
