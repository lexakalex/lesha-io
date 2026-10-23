# Overview

## What lesha-io is

The public website **lesha.io** — a single static page that is the client
download front door. There is no build system and no framework:

| path | purpose |
|---|---|
| `index.html` | the whole site: terminal-style ASCII-art landing page with inline CSS, an Android install block (QR + APK link) and a Windows installer link. Carries a `<!-- build: __BUILD_ID__ -->` marker that CI stamps with the short SHA + UTC time. |
| `qr.svg` | QR code encoding the Android APK link |
| `.github/workflows/deploy.yml` | on push to `main`: stamp the build marker, `wrangler pages deploy` to the Cloudflare Pages project `lesha-io` |

**Download links point at `dl.lesha.io`, not at this repo** —
`https://dl.lesha.io/android/lesha-tunnel-latest-arm64.apk` and
`https://dl.lesha.io/windows/lesha-tunnel-setup-latest.exe`. Those `latest`
objects are published by lesha-tunnel's release pipeline; this repo only links
to them. A broken download is almost always a release-feed problem, not a page
problem.

## Rules that bite

- **A push to `main` is live** — CI deploys every push straight to production.
  Check links and version references against the real release feed before
  pushing.
- If the APK URL changes, regenerate `qr.svg` — the QR encodes the URL and will
  silently keep pointing at the old one.

## Docs in this directory

- [issue-tracking.md](issue-tracking.md) — the fleet issue tracker: this repo's
  bugs/features file into `lexakalex/terrabond` issues with the `repo:lesha-io`
  label
