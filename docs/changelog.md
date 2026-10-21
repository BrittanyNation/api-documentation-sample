# Changelog

## v1.3 — 2026-09-15
- Added `channel` field to alert creation (`email`, `slack`, `webhook`).
- Rate limit headers now included on all responses.

## v1.2 — 2026-06-02
- New endpoint: `GET /dashboards/{id}`.
- Deprecated `GET /metrics/all` (removed in v2). Use `GET /metrics`.

## v1.1 — 2026-02-20
- Error responses standardized on the format in [Errors](errors.md).

## v1.0 — 2025-11-10
- Initial public release: metrics and alerts resources.
