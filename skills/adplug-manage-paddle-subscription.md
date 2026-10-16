---
name: adplug-manage-paddle-subscription
description: Manage a user's Paddle subscription by retrieving, changing, and cancelling it.
api: openapi/adplug.json
operations:
- get_paddle_subscription_api_users__user_id__paddle_subscription_get
- paddle_change_plan_api_users__user_id__paddle_change_plan_post
- paddle_cancel_current_sub_api_users__user_id__paddle_cancel_current_sub_post
generated: '2026-10-15'
method: generated
generator: extract-docs-artifacts.py skills (local)
source: openapi/adplug.json ; every operationId checked against the contract
---

# adplug-manage-paddle-subscription

Manage a user's Paddle subscription by retrieving, changing, and cancelling it.

## Steps

1. 1. Retrieve the current subscription with `get_paddle_subscription_api_users__user_id__paddle_subscription_get` (requires path parameter `user_id`).
2. 2. Change the subscription plan with `paddle_change_plan_api_users__user_id__paddle_change_plan_post` (requires `user_id` and request body fields `plan_id`, `quantity`).
3. 3. Cancel the active subscription with `paddle_cancel_current_sub_api_users__user_id__paddle_cancel_current_sub_post` (requires `user_id`).

## Rules

- All requests must include an `Authorization: Bearer <token>` header (HTTPBearer auth scheme).
- POST endpoints are not idempotent; avoid repeating calls unless the operation is intended to be retried.
- If a request fails, the API returns standard HTTP error codes (e.g., 400 for bad request, 401 for unauthorized, 404 for not found, 500 for server error).
