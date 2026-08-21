# RevoTrack MCP Metadata

Public OAuth Client ID Metadata Documents (CIMD) used by RevoTrack MCP integrations.

These files are intentionally public. They identify OAuth clients and their callback URIs, but contain no credentials, tokens, passwords, API keys, or user data.

## Contents

- `codex-flespi-development-client.json`: CIMD for Codex access to the RevoTrack Flespi Development realm.

## Security

OAuth authorization is protected by the Flespi realm user, the Realm's allowed-client list, and PKCE. Do not add any secret to this repository.
