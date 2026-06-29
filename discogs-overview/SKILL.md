---
name: discogs-overview
description: >-
  Cross-cutting conventions for the Discogs API (api.discogs.com) that apply to
  every endpoint. Make sure to use this skill whenever a Discogs request touches
  general API behaviour rather than one specific resource — setting the
  mandatory User-Agent, handling rate limiting (X-Discogs-Ratelimit headers,
  60/min authenticated vs 25/min unauthenticated), paginating list responses
  (page / per_page, Link header, pagination object), pinning an API version via
  the Accept header, returning JSONP, or interpreting HTTP status codes
  (200/201/204/401/403/404) and empty responses from Discogs.
---

# Discogs API — Overview & Conventions

Base URL: `https://api.discogs.com`. RESTful, JSON, currently **v2** only.

## User-Agent (mandatory)
Every request must send a unique, descriptive `User-Agent` (RFC 1945 style),
e.g. `MyDiscogsClient/1.0 +http://mydiscogsclient.org`. Missing or generic
agents get an **empty response** or are silently blocked. Don't copy the docs'
examples verbatim.

## Rate limiting
Throttled by source IP: **60 req/min authenticated, 25 req/min unauthenticated**
(moving 60-second window). Track via response headers:
`X-Discogs-Ratelimit`, `X-Discogs-Ratelimit-Used`, `X-Discogs-Ratelimit-Remaining`.
A unique User-Agent is required to get the max rate. Throttle locally.

## Pagination
List endpoints default to **50 items/page**, max **100**. Use `?page=` and
`?per_page=`. Responses carry a `Link` header (rel=next/prev/first/last) and a
`pagination` object (`page`, `pages`, `items`, `per_page`, `urls`).

## Versioning (Accept header)
Future-proof with `Accept: application/vnd.discogs.v2.<format>+json` where
`<format>` is `discogs` (default), `html`, or `plaintext`. Unknown/absent →
defaults to `discogs`.

## JSONP
Add `?callback=name`; status and headers are wrapped in the body
(`{"meta":{"status":200},"data":{…}}`) since JSONP can't read real headers.

## HTTP status codes
| Code | Meaning |
|---|---|
| 200 OK | Success, data in body |
| 201 Created | POST created a resource; new ID in body |
| 204 No Content | Success, empty body |
| 401 Unauthorized | Needs authentication (see `discogs-authentication`) |
| 403 Forbidden | Authenticated but not allowed (e.g. editing another user) |
| 404 Not Found | Often a modified/signed image URL or wrong ID |

Auth details live in [[discogs-authentication]]. Full text, FAQ, and client
library links are in [reference.md](reference.md).
