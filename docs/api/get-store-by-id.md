---
# markdownlint-disable
# vale off
# tags used by just-the-docs theme
layout: default
parent: store resource
nav_order: 2
# tags used by AI files
description: Get `store` resource by ID
topic_type: reference
tags: 
    - api
categories:
    - api-reference
ai_relevance: high
importance: 8
prerequisites: 
    - ../docs/quickstart.md
related_pages: 
    - /store.md
examples: []
test:
    test_apps:
        - json-server@0.17.4
    server_url: localhost:3000
    local_database: /api/pizzaSlicedb.json
    testable:
        - GET example
api_endpoints: 
    - /stores
version: "v1.0"
last_updated: "2026-11-21"
# vale  on
# markdownlint-enable
---

# Get store by ID

Returns an array of of `store` objects that contains
only the store requested by the `id` parameter,
if it exists.

Base endpoint:

```shell
{server_url}/stores
```

## Parameters

| Name | Type | Value | Description |
| ----- | ------ | ------ | ------------ |
| `id` | URL | number | The record ID of the `store` resource to return |

## Request headers

| Header | Value | Required |
| ------ | ----- | -------- |
| `Accept` | `application/json` | No |

## Request body

None.

## Response Body

Returns a `store` resource.

## Examples

### `GET` example request

```json

curl -G -H "Accept: application/json" \
    --url "http://localhost:3000/stores/st_102"
```

### `GET` example response

```json
  {
    "id": "st_102",
    "name": "SliceOrder Ballard",
    "address": {
      "line1": "5300 Ballard Ave NW",
      "city": "Seattle",
      "state": "WA",
      "zip": "98107"
    },
    "order_types": [
      "pickup",
      "delivery"
    ],
    "delivery_fee": 2,
    "hours": {
      "open": "11:00",
      "close": "22:00"
    },
    "timezone": "America/Los_Angeles",
    "open_now": true
  }
```

## Response status

| HTTP status value | Description |
| ------------- | ----------- |
| 200 | **Success:** Requested data returned successfully |
| 400 | **Error:** Bad request |
| ECONNREFUSED | Service is offline. Start, or restart the service and try again. |
