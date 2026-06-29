---
name: discogs-database
description: >-
  Reference for the Discogs database endpoints (api.discogs.com) — the read-only
  catalog of music metadata. Make sure to use this skill whenever the task
  involves fetching or searching Discogs Releases, Masters, Artists, or Labels,
  even if "database" isn't said: getting a release/master/artist/label by id,
  listing an artist's or label's releases, master versions, release stats and
  community/user ratings (including PUT/DELETE a user's rating), pulling release
  videos, or running /database/search by query, barcode, catalog number, type,
  genre, year, etc. Also use it when deciding which query-string filters or
  sort options a database call supports.
---

# Discogs API — Database

Read-only music catalog. Note: image URLs and the high rate-limit tier require
auth (Consumer Key/Secret or better — see [[discogs-authentication]]). Search
requires authentication.

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/releases/{release_id}{?curr_abbr}` | A single release (specific pressing) |
| GET | `/releases/{release_id}/rating/{username}` | A user's rating of a release |
| PUT | `/releases/{release_id}/rating/{username}` | Set the user's rating (auth) |
| DELETE | `/releases/{release_id}/rating/{username}` | Remove the user's rating (auth) |
| GET | `/releases/{release_id}/rating` | Community (average) rating |
| GET | `/releases/{release_id}/stats` | Release stats (have/want counts) |
| GET | `/masters/{master_id}` | A master release (groups all versions) |
| GET | `/masters/{master_id}/versions{?page,per_page}` | All versions of a master |
| GET | `/artists/{artist_id}` | An artist |
| GET | `/artists/{artist_id}/releases{?sort,sort_order}` | An artist's releases |
| GET | `/labels/{label_id}` | A label |
| GET | `/labels/{label_id}/releases{?page,per_page}` | A label's releases |
| GET | `/database/search?q={query}` | Search (auth required) |

`/database/search` filters: `type, title, release_title, credit, artist, anv,
label, genre, style, country, year, format, catno, barcode, track, submitter,
contributor`. `curr_abbr` controls the currency for marketplace pricing fields.

See [reference.md](reference.md) for full parameter and response-field details.
