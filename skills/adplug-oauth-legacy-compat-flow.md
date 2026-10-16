---
name: adplug-oauth-legacy-compat-flow
description: Perform the legacy OAuth compatibility flow by authorizing, exchanging the token, and registering the client.
api: openapi/adplug.json
operations:
- authorize_passthrough_authorize_get
- token_passthrough_token_post
- register_passthrough_register_post
generated: '2026-10-15'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/adplug.json ; every operationId checked against the contract
---

# adplug-oauth-legacy-compat-flow

Perform the legacy OAuth compatibility flow by authorizing, exchanging the token, and registering the client.

## Steps

1. 1. Call `authorize_passthrough_authorize_get` – requires the standard HTTP Bearer Authorization header if applicable.
2. 2. Call `token_passthrough_token_post` – requires the standard HTTP Bearer Authorization header if applicable.
3. 3. Call `register_passthrough_register_post` – requires the standard HTTP Bearer Authorization header if applicable.

## Rules

- Use an HTTP `Authorization: Bearer <token>` header for each request.
- All requests are non‑idempotent; repeat calls only if safe to do so.
