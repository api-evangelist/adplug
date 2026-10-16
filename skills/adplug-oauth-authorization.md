---
name: adplug-oauth-authorization
description: Perform an OAuth authorization flow for a specific ad platform.
api: openapi/adplug.json
operations:
- authorize_oauth_google_ads_authorize_get
- callback_oauth_google_ads_callback_get
generated: '2026-10-15'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/adplug.json ; every operationId checked against the contract
---

# adplug-oauth-authorization

Perform an OAuth authorization flow for a specific ad platform.

## Steps

1. 1. Call `authorize_oauth_google_ads_authorize_get` – send a GET request to `/oauth/google-ads/authorize` (no request body required).
2. 2. Receive the redirect URL and follow it to the provider's consent screen.
3. 3. After user consent, the provider redirects to your callback endpoint; call `callback_oauth_google_ads_callback_get` – send a GET request to `/oauth/google-ads/callback` with the query parameters returned by the provider (e.g., `code`).

## Rules

- Include an `Authorization: Bearer <token>` header for all requests (HTTPBearer scheme).
- The flow is not idempotent; repeat only if a new authorization is required.
