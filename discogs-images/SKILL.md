---
name: discogs-images
description: >-
  How Discogs API images work (api.discogs.com). Make sure to use this skill
  whenever the task involves retrieving artwork or photos for a Discogs release,
  artist, or label, or debugging image access — e.g. a 403/404 on an image URL,
  missing image fields in a response, or questions about whether image requests
  need authentication. Key point this skill captures: there is no standalone
  image endpoint; image URLs are fully-qualified signed HTTPS URLs embedded in
  other resources and only appear for authenticated requests.
---

# Discogs API — Images

The Image resource is a user-contributed image of a database object (Artist,
Release, Label, etc.). **Image requests require authentication and are rate
limited.**

## How to get images
- There is **no image endpoint to construct by hand**. Image keys on other
  resources are fully-qualified signed URLs (host + HTTPS protocol included).
- Authenticate via **OAuth or Discogs Auth** (see [[discogs-authentication]]),
  then fetch the object that contains the image (the release, user profile,
  etc.). The `images` field carries the HTTPS URL; requesting it succeeds.
- A bare unauthenticated request will **not** return image URLs (image URLs are
  unavailable to unauthenticated requests — Consumer Key/Secret or a token
  unlocks them).

## Common pitfall
Image URLs are **signed**. Editing any part (e.g. swapping the release id) breaks
the signature and yields 404/403. Use them exactly as returned.

See [reference.md](reference.md) for the original text.
