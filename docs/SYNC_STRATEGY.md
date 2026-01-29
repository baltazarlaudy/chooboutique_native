#synchronisation Strategy
Pull:
GET /mobile/sync/
Unified sync endpoint
Supports bidirectional sync:
- GET: Pull data from backend (with incremental sync)
- POST: Push local changes to backend (orders, inventory updates)
- Supports ETag/If-None-Match for efficient incremental sync.