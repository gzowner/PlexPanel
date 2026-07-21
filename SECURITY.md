# PlexPanel Security Guide

## Network exposure

Expose only the PlexPanel web port through a firewall or reverse proxy. The Control API binds to `127.0.0.1` by default. PostgreSQL and Redis remain on the internal Compose network.

Use HTTPS before exposing the panel outside a trusted private network. Set `COOKIE_SECURE=true` after HTTPS is active.

## Plex tokens

Account-sharing features require a token from the Plex account that owns the managed server. Tokens are encrypted in PostgreSQL with a key derived from `APP_SECRET`.

Protect `/opt/plexpanel/.env`. Losing or changing `APP_SECRET` requires re-entering stored Plex tokens.

## Administrator credentials

Generated credentials are stored at `/opt/plexpanel/panel-admin-credentials.txt`. Change the password after first login and keep this file restricted to root.

## Automatic enforcement

Session termination is disabled by default. Enable it only after confirming that Plex usernames in customer records match the names reported by active sessions.

## Diagnostics

Diagnostic bundles attempt to redact tokens, passwords, and secrets. Review a bundle before sending it elsewhere. Never publish live Plex tokens, `.env` files, customer addresses, database dumps, or diagnostic archives in a public issue.
