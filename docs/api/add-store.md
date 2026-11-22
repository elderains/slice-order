---
# markdownlint-disable
# vale off
# tags used by just-the-docs theme
layout: default
parent: store resource
nav_order: 3
# tags used by AI files
description: Add a `store` resource
topic_type: reference
tags: 
    - api
categories:
    - api-reference
ai_relevance: high
importance: 8
prerequisites: 
    - /docs/quickstart
related_pages: 
    - docs/store
examples: []
test:
    test_apps:
        - json-server@0.17.4
    server_url: localhost:3000
    local_database: /api/pizzaSlicedb.json
    testable:
        - POST example
api_endpoints: 
    - /stores
version: "v1.0"
last_updated: "2026-11-21"
# vale  on
# markdownlint-enable
---

# Add a store

Returns an array of a new `store` object based on
specifications in the `POST` request.

Base endpoint:

```shell
{server_url}/stores
```

## Parameters

None.

## Request headers

| Header | Value | Required |
| ------ | ----- | -------- |
| `Content-Type` | `application/json` | No |

## Request body

```json
{
    "id": "st_106",
    "name": "SliceOrder Space Needle",
    "address": {
      "line1": "400 Broad St",
      "city": "Seattle",
      "state": "WA",
      "zip": "98109"
    },
    "order_types": [
      "pickup",
      "delivery"
    ],
    "delivery_fee": 2,
    "hours": {
      "open": "10:00",
      "close": "18:00"
    },
    "timezone": "America/Los_Angeles",
    "open_now": true
  }
```

## Response Body

Returns a new `store` resourse as specified in the request body.

## Examples

### `POST` example request

```json
curl -X POST http://localhost:3000/stores \
  -H "Content-Type: application/json" \
  -d '
  {
    "id": "st_106",
    "name": "SliceOrder Space Needle",
    "address": {
      "line1": "400 Broad St",
      "city": "Seattle",
      "state": "WA",
      "zip": "98109"
    },
    "order_types": [
      "pickup",
      "delivery"
    ],
    "delivery_fee": 2,
    "hours": {
      "open": "10:00",
      "close": "18:00"
    },
    "timezone": "America/Los_Angeles",
    "open_now": true
}'
```

### `POST` example response

```json
   {
    "id": "st_106",
    "name": "SliceOrder Space Needle",
    "address": {
      "line1": "400 Broad St",
      "city": "Seattle",
      "state": "WA",
      "zip": "98109"
    },
    "order_types": [
      "pickup",
      "delivery"
    ],
    "delivery_fee": 2,
    "hours": {
      "open": "10:00",
      "close": "18:00"
    },
    "timezone": "America/Los_Angeles",
    "open_now": true
}'
```

## Response status

| HTTP status value | Description |
| ------------- | ----------- |
| 200 | **Success:** Requested data returned successfully |
| 400 | **Error:** Bad request |
| ECONNREFUSED | Service is offline. Start, or restart the service and try again. |
