---
name: discogs-user-identity
description: >-
  Reference for the Discogs user identity and profile endpoints
  (api.discogs.com). Make sure to use this skill whenever the task involves the
  authenticated user or a user profile: confirming who a token/OAuth credential
  belongs to via oauth/identity, reading a user profile, editing your own
  profile, or listing a user's submissions and contributions to the database.
  Use oauth/identity as the canonical "is my auth working / who am I" check
  after wiring up authentication.
---

# Discogs API — User Identity

Who the credentials belong to, plus public profile data. Editing a profile is
per-user (auth required — see [[discogs-authentication]]).

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/oauth/identity` | The authenticated user (id, username, etc.) — auth sanity check |
| GET | `/users/{username}` | A user's profile |
| POST | `/users/{username}` | Edit **your own** profile (auth; 403 for others) |
| GET | `/users/{username}/submissions` | The user's database submissions |
| GET | `/users/{username}/contributions{?sort,sort_order}` | The user's contributions |

`GET /oauth/identity` is the standard test that authentication is set up
correctly: a success response identifies the authenticated user.

See [reference.md](reference.md) for editable profile fields and responses.
