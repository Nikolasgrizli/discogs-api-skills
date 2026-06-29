---
name: discogs-inventory-export
description: >-
  Reference for the Discogs inventory export endpoints (api.discogs.com). Make
  sure to use this skill whenever the task involves exporting a seller's Discogs
  inventory to CSV — kicking off an export, polling recent exports, checking the
  status of a specific export by id, or downloading the finished CSV file. This
  is a per-user, asynchronous flow (request → poll status → download), distinct
  from inventory upload; use it when bulk-reading inventory out of Discogs.
---

# Discogs API — Inventory Export

Asynchronous CSV export of your own inventory (per-user, auth required —
see [[discogs-authentication]]). Flow: **POST to start → poll status → download**.

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| POST | `/inventory/export` | Start an export; `Location` header returns the export URL |
| GET | `/inventory/export` | List recent exports (paginated) |
| GET | `/inventory/export/{id}` | Status/details of one export |
| GET | `/inventory/export/{id}/download` | Download the finished CSV |

An export item carries `status`, `created_ts`, `finished_ts`, `url`,
`download_url`, `filename`, `id`. Wait for `status: success` before downloading.

See [reference.md](reference.md) for full request/response examples.
