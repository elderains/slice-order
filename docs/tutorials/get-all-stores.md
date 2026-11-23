---
# markdownlint-disable
# vale off
# tags used by just-the-docs theme
layout: default
parent: Tutorials
nav_order: 2
# tags used by AI files
description: Get all `store` resources
topic_type: tutorial
tags:
    - api
categories: 
    - tutorial
ai_relevance: high
importance: 6
prerequisites: 
    - /quickstart
related_pages: []
examples: []
api_endpoints: 
    - POST /users
version: "v1.0"
last_updated: "2026-11-19"
# vale  on
# markdownlint-enable
---
# Tutorial - Get a Store

<!-- vale Google.Acronyms = off -->
SliceOrder is a REST API for pizza franchises
to manage orders and menus.

A useful function of the app is to retreive location,
hours, and delivery information for
a [store](../api/store.md).

**In this tutorial, you'll learn**:

- How to retrieve a list of all SliceOrder pizza store locations.

The `GET` method utilized here allows you to retrieve
a list of `stores` in the service.

This can be useful when you need to know where all SliceOrder
pizza stores are and need to determine the closest one for
a delivery order.

## Prerequisites

Make sure you've completed the [Quickstart guide](../../docs/quickstart.md)
topic on the development system you'll use for this tutorial.

## Step 1: Get the list of stores

1. Make sure your local service is running, or start it by using this command, if it's not.

    ```shell
    cd <your-github-workspace>/to-do-service/api
    json-server -w pizzaSlicedb.json
    ```

2. Request a list of stores
with the following `curl` command, substituting
your actual server URL for
`{server_url}`:

    ```bash
    curl {server_url}/stores
    ```

The response should be a list of `stores` and their
associated properties, like address, order type, etc.:

```json
 {
    "id": "st_101",
    "name": "SliceOrder Capitol Hill",
    "address": {
      "line1": "1420 E Pine St",
      "city": "Seattle",
      "state": "WA",
      "zip": "98122"
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
  },
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

## Wrap-up and next steps

Nice &mdash; you retrieved a list of `stores`.

In the future, if you'd like to request the information
for a *specific* store, try the **[Get store by ID tutorial](get-store-by-id.md)**.

If you got stuck, refer to the **Troubleshooting** section below.

### Related topics

- [**Add your first store >**](../tutorials/enroll-a-new-user.md)

- [**Edit store details >**](../tutorials/add-a-new-task.md)

## Troubleshooting

- **Returned a response of `{}`**: make sure you input
the command correctly, and didn't misspell "stores".

***
[**Tutorials**](tutorials.md) |
[**API Reference**](../../docs/index.md#api-reference-docs)
| Copyright &copy; elderains
