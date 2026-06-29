---
name: discogs-user-collection
description: >-
  Reference for the Discogs user collection endpoints (api.discogs.com). Make
  sure to use this skill whenever the task involves a user's Discogs collection,
  even if "collection" isn't said: listing or creating collection folders;
  adding a release to a folder; moving, rating, or removing a release instance;
  listing collection items by folder or by release; reading or editing custom
  collection fields; or computing the collection's monetary value. Most write
  operations are per-user and need a User token or OAuth.
---

# Discogs API — User Collection

A user's owned releases, organized into folders, with custom fields and a value
estimate. Writes are per-user (auth required — see [[discogs-authentication]]).
Folder `0` = "All", folder `1` = "Uncategorized".

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/users/{username}/collection/folders` | List folders |
| POST | `/users/{username}/collection/folders` | Create a folder (auth) |
| GET | `/users/{username}/collection/folders/{folder_id}` | A folder's metadata |
| POST | `/users/{username}/collection/folders/{folder_id}` | Rename a folder (auth) |
| DELETE | `/users/{username}/collection/folders/{folder_id}` | Delete a folder (auth) |
| GET | `/users/{username}/collection/releases/{release_id}` | Find a release across folders |
| GET | `/users/{username}/collection/folders/{folder_id}/releases` | Items in a folder |
| POST | `/users/{username}/collection/folders/{folder_id}/releases/{release_id}` | Add a release to a folder (auth) |
| POST | `…/releases/{release_id}/instances/{instance_id}` | Move/rate an instance (auth) |
| DELETE | `…/releases/{release_id}/instances/{instance_id}` | Remove an instance (auth) |
| GET | `/users/{username}/collection/fields` | List custom fields |
| POST | `…/instances/{instance_id}/fields/{field_id}{?value}` | Set a custom field value (auth) |
| GET | `/users/{username}/collection/value` | Min/median/max collection value (auth) |

(A release can appear multiple times; each copy is an **instance** with its own
`instance_id`, rating, and custom-field values.)

See [reference.md](reference.md) for parameters, pagination, and responses.
