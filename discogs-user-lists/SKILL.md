---
name: discogs-user-lists
description: >-
  Reference for the Discogs user lists endpoints (api.discogs.com). Make sure to
  use this skill whenever the task involves Discogs user-curated Lists — the
  named, ordered collections of database items (releases, artists, labels) a user
  creates: listing a user's lists, or fetching the items of a specific list by
  id. Distinct from a user's collection or wantlist; use this for the "Lists"
  feature specifically.
---

# Discogs API — User Lists

User-curated, named lists of database items (releases, artists, labels).
Read-only via the API; private lists need the owner's auth
(see [[discogs-authentication]]).

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/users/{username}/lists` | List a user's public lists (paginated) |
| GET | `/lists/{list_id}` | Items in a specific list |

See [reference.md](reference.md) for response fields.
