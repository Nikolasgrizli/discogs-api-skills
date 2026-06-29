---
name: discogs-user-wantlist
description: >-
  Reference for the Discogs user wantlist endpoints (api.discogs.com). Make sure
  to use this skill whenever the task involves a user's Discogs wantlist (the
  list of releases they want): listing the wantlist, adding a release to it, or
  updating/removing a wantlist entry including its notes and rating. Adding,
  editing, and deleting wants are per-user and need a User token or OAuth.
---

# Discogs API — User Wantlist

Releases a user wants. Reads of a public wantlist are open; writes are per-user
(auth required — see [[discogs-authentication]]).

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/users/{username}/wants` | List the wantlist (paginated) |
| PUT | `/users/{username}/wants/{release_id}{?notes,rating}` | Add a release to the wantlist (auth) |
| POST | `/users/{username}/wants/{release_id}{?notes,rating}` | Update a want's notes/rating (auth) |
| DELETE | `/users/{username}/wants/{release_id}` | Remove a want (auth) |

`notes` = free text; `rating` = 0–5. See [reference.md](reference.md) for
response fields.
