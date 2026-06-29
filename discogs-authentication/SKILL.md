---
name: discogs-authentication
description: >-
  Reference for authenticating with the Discogs API (api.discogs.com). Make sure
  to use this skill whenever the task touches Discogs auth, credentials, tokens,
  or signed requests — even if "authentication" isn't said outright. Triggers
  include: choosing between a User (personal access) token, a Consumer
  Key/Secret pair (Discogs Auth), or the full OAuth 1.0a flow; building or fixing
  the Authorization header; wiring up the oauth/request_token, oauth/authorize,
  oauth/access_token or oauth/identity endpoints; getting 401/403 or
  "authentication failed" from Discogs; or troubleshooting why image URLs, the
  higher rate-limit tier, or per-user resources (marketplace orders, a user's
  collection or wantlist, private inventory fields) are missing from responses.
---

# Discogs API — Authentication

Discogs offers three ways to authenticate. Pick based on what the request needs.

## Quick decision

| Method | Identifies a user? | Image URLs + high rate limit? | Use when |
|---|---|---|---|
| No auth | No | No | Public, low-volume reads only |
| **Discogs Auth — Consumer Key/Secret** | No | Yes | 3rd-party app reads that don't need a specific user |
| **Discogs Auth — User token** | Yes (token holder only) | Yes | Accessing **your own** account (simplest secure option) |
| **OAuth 1.0a** | Yes (any user, on their behalf) | Yes | App acting for other users' accounts |

Per-user resources — marketplace orders, private inventory fields, private
collections — require a **token** or **OAuth**; a bare Consumer Key/Secret will
not grant them.

## Discogs Auth (simple)

Send credentials in the query string **or** an `Authorization` header (HTTPS required):

```
curl "https://api.discogs.com/database/search?q=Nirvana&token=abcxyz123456"
curl "https://api.discogs.com/database/search?q=Nirvana&key=foo123&secret=bar456"

curl "https://api.discogs.com/database/search?q=Nirvana" \
  -H "Authorization: Discogs token=abcxyz123456"
curl "https://api.discogs.com/database/search?q=Nirvana" \
  -H "Authorization: Discogs key=foo123, secret=bar456"
```

## OAuth 1.0a (act on behalf of users)

Three server-side endpoints; PLAINTEXT signature recommended over HTTPS
(`oauth_signature` = `consumer_secret&`). Flow:

1. Get Consumer Key/Secret from Developer Settings.
2. `GET https://api.discogs.com/oauth/request_token` → request token + secret.
3. Redirect user to `https://discogs.com/oauth/authorize?oauth_token=…` → verifier (15 min TTL).
4. `POST https://api.discogs.com/oauth/access_token` → **access token + secret (do not expire; store them)**.
5. Sign every request with the access token/secret. Test with `GET https://api.discogs.com/oauth/identity`.

Always send a unique `User-Agent`. Invalid/expired OAuth requests return `400 Bad Request`.

## Full reference

See [reference.md](reference.md) for the complete text: registration steps,
endpoint URLs, per-step request headers, response fields, and the full
credentials comparison.
