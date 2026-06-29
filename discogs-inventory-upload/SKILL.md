---
name: discogs-inventory-upload
description: >-
  Reference for the Discogs inventory upload endpoints (api.discogs.com). Make
  sure to use this skill whenever the task involves bulk-changing a seller's
  Discogs inventory via CSV — adding new listings, changing existing listings,
  or deleting listings in bulk, plus checking recent uploads or the status of a
  specific upload by id. Use it when you need the required/optional CSV columns
  and conditions for each operation (add / change / delete). This is the
  per-user, asynchronous counterpart to inventory export.
---

# Discogs API — Inventory Upload

Asynchronous **CSV upload** to mutate your own inventory in bulk (per-user, auth
required — see [[discogs-authentication]]). Each operation takes a CSV with a
specific column set; uploads are processed asynchronously, then polled.

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| POST | `/inventory/upload/add` | Add new listings from a CSV |
| POST | `/inventory/upload/change` | Change existing listings from a CSV |
| POST | `/inventory/upload/delete` | Delete listings from a CSV |
| GET | `/inventory/upload` | List recent uploads (paginated) |
| GET | `/inventory/upload/{id}` | Status/details of one upload |

## CSV essentials
- **add** — required: `release_id`, `price`, `media_condition`; plus optional
  fields (sleeve condition, comments, etc.).
- **change** — required: `listing_id`; at least **one** optional field to change.
- **delete** — required: `listing_id` only.

Exact required vs optional columns and allowed condition values are in
[reference.md](reference.md) — read it before constructing the CSV.
