# RevoTrack MCP Metadata

Public OAuth Client ID Metadata Documents (CIMD) used by RevoTrack MCP integrations.

These files are intentionally public. They identify OAuth clients and their callback URIs, but contain no credentials, tokens, passwords, API keys, or user data.

## Contents

- `codex-flespi-development-client.json`: CIMD for Codex access to the RevoTrack Flespi Development realm.
- `claude-flespi-development-client.json`: CIMD for Claude Code access to the same realm. Fixed callback `http://localhost:47213/callback`, matching `oauth.callbackPort` in `RevoTrack-Workspace/.mcp.json`.
- `codex-flespi-production-client.json`: CIMD for Codex read-only access to the RevoTrack Flespi Production realm. Its redirect URI must match the callback Codex uses for that server in `~/.codex/config.toml`.
- `claude-flespi-production-client.json`: CIMD for Claude Code read-only access to the RevoTrack Flespi Production realm. Fixed callback `http://localhost:47214/callback` (distinct from Development so both servers can be configured), matching the `flespi-prod` entry in `RevoTrack-Workspace/.mcp.json`. The realm user's token must be restricted to GET.

Each file's `client_id` is its own raw GitHub URL, so a file must be pushed to `main` before its client can sign in, and the realm must list that URL among its allowed clients. Changing a callback means changing both the CIMD and the client configuration.

## Security

OAuth authorization is protected by the Flespi realm user, the Realm's allowed-client list, and PKCE. Do not add any secret to this repository.
