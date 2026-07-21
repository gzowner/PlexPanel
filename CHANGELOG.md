# Changelog

## 0.1.0 — Initial early-access release

### Added

- Standalone Docker control plane with PostgreSQL, Redis, FastAPI worker, and Nginx.
- Multi-server Plex registry with encrypted account tokens.
- Server identity, version, platform, health, and primary-server state.
- Plex library inventory, scan, metadata refresh, empty-trash, and activity support.
- Scheduled library scans.
- Plex account invitation and library-share synchronization.
- Import of existing accepted shares and pending invitations.
- Packages with duration, stream limits, downloads, and reseller credit cost.
- Master-reseller, reseller, and sub-reseller logins.
- Customer expiration, renewal, suspension, and deletion workflows.
- Fleet-wide active playback sessions and session termination.
- Central playback-history storage.
- Optional connection-limit enforcement, disabled by default.
- Dashboard, Operations, Audit, diagnostics, backup, repair, and upgrade tooling.

### Deliberately excluded

- STRM generation
- Media mirroring
- M3U/XMLTV and Live TV
- Media proxying
- Billing and payment processing
