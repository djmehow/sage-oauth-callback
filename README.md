# sage-oauth-callback

Static OAuth 2.0 redirect (callback) page for Tatus Consultancy's Sage Accounting
integration, served via GitHub Pages at **https://sage-oauth.tatus.co.za/**.

## What it is
When you sign in to Sage (Sage ID) during the Authorization Code Grant, Sage
redirects your browser here with `?code=…&state=…`. This page just reads those
values out of the URL and displays the authorization code for you to copy back
into the reporting tool (`python auth.py login`).

## Why it's public and safe
- It is **static HTML/JS only** — no server, no backend, no database.
- It **never sees the `client_secret`** and never performs the token exchange;
  that happens locally in the private `sage-reporting-service` tool.
- The authorization code it displays is single-use and worthless without the
  client secret, so there are no secrets to protect here.

The actual integration code lives in the private repo `sage-reporting-service`.
