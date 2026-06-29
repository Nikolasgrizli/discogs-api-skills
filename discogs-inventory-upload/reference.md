# Discogs API — Inventory Upload

## Add inventory

### POST /inventory/upload/add
Upload a CSV of listings to add to your inventory. File structure ¶ The file you upload must be a comma-separated CSV. The first row must be a header with lower case field names. Here’s an example: release_id,price,media_condition,comments 123,1.50,Mint (M),Comments about this release for sale 456,2.50,Near Mint (NM or M-),More comments 7890,3.50,Good (G),Signed vinyl copy Things to note: ¶ These listings will be marked “For Sale” immediately. Currency information will be pulled from your marketplace settings. Any fields that aren’t optional or required will be ignored. Required fields ¶ release_id - Must be a number. This value corresponds with the Discogs database Release ID. price - Must be a number. media_condition - Must be a valid condition (see below). Optional fields ¶ sleeve_condition - Must be a valid condition (see below). comments accept_offer - Must be Y or N. location - Private free-text field to help identify an item’s physical location. external_id - Private notes or IDs for your own reference. weight - In grams. Must be a non-negative integer. format_quantity - Number of items that this item counts as (for shipping). Conditions ¶ When you specify a media condition, it must exactly match one of these: Mint (M) Near Mint (NM or M-) Very Good Plus (VG+) Very Good (VG) Good Plus (G+) Good (G) Fair (F) Poor (P) Sleeve condition may be any of the above, or: Not Graded Generic No Cover

**Parameters:**
- `upload` (file, required) — The CSV file of items to add to your inventory.

## Change inventory

### POST /inventory/upload/change
Upload a CSV of listings to change in your inventory. File structure ¶ The file you upload must be a comma-separated CSV. The first row must be a header with lower case field names. Here’s an example: release_id,price,media_condition,comments 123,1.50,Mint (M),Comments about this release for sale 456,2.50,Near Mint (NM or M-),More comments 7890,3.50,Good (G),Signed vinyl copy Things to note: ¶ These listings will be marked “For Sale” immediately. Currency information will be pulled from your marketplace settings. Any fields that aren’t optional or required will be ignored. Required fields ¶ release_id - Must be a number. This value corresponds with the Discogs database Release ID. Optional fields (at least one required) ¶ price - media_condition - Must be a valid condition (see below). sleeve_condition - Must be a valid condition (see below). comments accept_offer - Must be Y or N. external_id - Private notes or IDs for your own reference. location - Private free-text field to help identify an item’s physical location. weight - In grams. Must be a non-negative integer. format_quantity - Number of items that this item counts as (for shipping). Conditions ¶ When you specify a media condition, it must exactly match one of these: Mint (M) Near Mint (NM or M-) Very Good Plus (VG+) Very Good (VG) Good Plus (G+) Good (G) Fair (F) Poor (P) Sleeve condition may be any of the above, or: Not Graded Generic No Cover

**Parameters:**
- `upload` (file, required) — The CSV file of items to alter in your inventory.

## Delete inventory

### POST /inventory/upload/delete
Upload a CSV of listings to delete from your inventory. File structure ¶ The file you upload must be a comma-separated CSV. The first row must be a header with lower case field names. Here’s an example: listing_id 12345678 98765432 31415926 Required fields ¶ listing_id - Must be a number. This is the ID of the listing you wish to delete.

**Parameters:**
- `upload` (file, required) — The CSV file listing items to remove from your inventory.

## Get recent uploads

### GET /inventory/upload
Get a list of all recent inventory uploads. Accepts Pagination parameters.

**Example response:**
```json
{
  "items": [
    {
      "status": "success",
      "results": "CSV file contains 1 records.<p>Processed 1 records.",
      "created_ts": "2017-12-18T09:20:28",
      "finished_ts": "2017-12-18T09:20:29",
      "filename": "add.csv",
      "type": "change",
      "id": 119615
    }
  ],
  "pagination": {
    "per_page": 50,
    "items": 1,
    "page": 1,
    "urls": {},
    "pages": 1
  }
}
```

## Get an upload

### GET /inventory/upload/{id}
Get details about the status of an inventory upload.

**Parameters:**
- `id` (number, required) — Id of the export.

**Example response:**
```json
{
  "status": "success",
  "results": "CSV file contains 1 records.<p>Processed 1 records.",
  "created_ts": "2017-12-18T09:20:28",
  "finished_ts": "2017-12-18T09:20:29",
  "filename": "add.csv",
  "type": "change",
  "id": 119615
}
```
