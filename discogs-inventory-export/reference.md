# Discogs API — Inventory Export

## Export your inventory

### POST /inventory/export
Request an export of your inventory as a CSV.

## Get recent exports

### GET /inventory/export
Get a list of all recent exports of your inventory. Accepts Pagination parameters.

**Example response:**
```json
{
  "items": [
    {
      "status": "success",
      "created_ts": "2018-09-27T12:59:02",
      "url": "https://api.discogs.com/inventory/export/599632",
      "finished_ts": "2018-09-27T12:59:02",
      "download_url": "https://api.discogs.com/inventory/export/599632/download",
      "filename": "cburmeister-inventory-20180927-1259.csv",
      "id": 599632
    }
  ],
  "pagination": {
    "per_page": 50,
    "items": 15,
    "page": 1,
    "urls": {},
    "pages": 1
  }
}
```

## Get an export

### GET /inventory/export/{id}
Get details about the status of an inventory export.

**Parameters:**
- `id` (number, required) — Id of the export.

**Example response:**
```json
{
  "status": "success",
  "created_ts": "2018-09-27T12:50:39",
  "url": "https://api.discogs.com/inventory/export/599632",
  "finished_ts": "2018-09-27T12:59:02",
  "download_url": "https://api.discogs.com/inventory/export/599632/download",
  "filename": "cburmeister-inventory-20180927-1259.csv",
  "id": 599632
}
```

## Download an export

### GET /inventory/export/{id}/download
Download the results of an inventory export.

**Parameters:**
- `id` (number, required) — Id of the export.
