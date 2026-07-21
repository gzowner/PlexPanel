# PlexPanel v0.1.0 Validation

## Completed in the build environment

- Python source compiled successfully.
- Shell scripts passed `bash -n`.
- Docker Compose YAML parsed successfully.
- Browser JavaScript passed Node syntax validation.
- Static HTML identifiers were unique.
- Runtime code contains no Jellyfin, Emby, M3U, XMLTV, or STRM components.
- PostgreSQL schema definitions and indexes were reviewed.
- FastAPI loaded successfully with the pinned runtime dependencies.
- The generated bcrypt environment assignment was verified under `set -u`.
- API routes were checked for duplicate method/path registrations.
- Mocked Plex client tests covered URL normalization, library inventory, scans, metadata refresh, empty trash, access updates, invitations, and pending-invitation cancellation.
- ZIP extraction, CRC, executable permissions, and internal SHA-256 manifests were verified during packaging.

## Not available in the build environment

- Docker daemon
- PostgreSQL runtime
- Redis runtime
- A live Plex Media Server
- A live Plex owner-account token
- Plex invitation email acceptance

Complete `TEST-PLEX.md` before production use.
