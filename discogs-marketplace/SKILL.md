---
name: discogs-marketplace
description: >-
  Reference for the Discogs Marketplace endpoints (api.discogs.com). Make sure to
  use this skill whenever the task involves selling or buying on Discogs, even if
  "marketplace" isn't said: listing a seller's inventory; creating, editing, or
  deleting a marketplace listing; reading or updating an order and its status;
  sending or listing order messages; calculating the Discogs selling fee (with or
  without currency); fetching price suggestions or release marketplace stats
  (lowest price / num for sale). Orders, order messages, and managing your own
  inventory are per-user resources and need a User token or OAuth.
---

# Discogs API — Marketplace

Buy/sell layer over the catalog. **Orders, order messages, and editing your own
listings/inventory are per-user — require a User token or OAuth**
(see [[discogs-authentication]]). `curr_abbr` selects the currency.

## Endpoints
| Method | Path | Purpose |
|---|---|---|
| GET | `/users/{username}/inventory{?status,sort,sort_order}` | A seller's inventory |
| GET | `/marketplace/listings/{listing_id}{?curr_abbr}` | View a listing |
| POST | `/marketplace/listings/{listing_id}{?curr_abbr}` | Edit a listing (auth) |
| DELETE | `/marketplace/listings/{listing_id}` | Delete a listing (auth) |
| POST | `/marketplace/listings` | Create a new listing (auth) |
| GET | `/marketplace/orders/{order_id}` | View an order (auth) |
| POST | `/marketplace/orders/{order_id}` | Update an order / its status (auth) |
| GET | `/marketplace/orders{?status,created_after,created_before,sort,sort_order}` | List your orders (auth) |
| GET | `/marketplace/orders/{order_id}/messages` | List order messages (auth) |
| POST | `/marketplace/orders/{order_id}/messages` | Add an order message (auth) |
| GET | `/marketplace/fee/{price}` | Selling fee for a price (default currency) |
| GET | `/marketplace/fee/{price}/{currency}` | Selling fee in a given currency |
| GET | `/marketplace/price_suggestions/{release_id}` | Suggested prices by condition (auth) |
| GET | `/marketplace/stats/{release_id}{?curr_abbr}` | Lowest price + number for sale |

New-listing fields: `release_id, condition, sleeve_condition, price, comments,
allow_offers, status, external_id, location, weight, format_quantity`.

See [reference.md](reference.md) for parameters, allowed values, and responses.
