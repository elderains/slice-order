---
# markdownlint-disable
# vale off
# tags used by just-the-docs theme
layout: default
parent: Tutorials
nav_order: 1
# tags used by AI files
description: Add a store
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
# Tutorial - Add a Store

<!-- vale Google.Acronyms = off -->
SliceOrder is a REST API for pizza franchises
to manage orders and menus.

**In this tutorial, you'll learn**:

- How add [stores](../api/store.md)
to the API.

The `POST` method utilized here allows you to create
new `store` resources in the service.

Use this as your business expands and you add
additional SliceOrder establishments.

## Prerequisites

Make sure you've completed the [Quickstart guide](../../docs/quickstart.md)
topic on the development system you'll use for this tutorial.

## Step 1: Input your store's properties

1. Copy and paste the code sample below into an editor
of your choice and edit or replace the values with
correct ones for your new store.

For a description of each property, see the [`stores` reference](../api/store.md).

```json
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
```

## Step 2: Send your Request

1. Make sure your local service is running, or start it by using this command, if it's not.

    ```shell
    cd <your-github-workspace>/to-do-service/api
    json-server -w pizzaSlicedb.json
    ```

2. `POST` a list of stores with the following `curl`
command, substituting your actual server URL for
`{server_url}` and your own store's values:

    ```bash
    curl -X POST {server_url}/stores \
    -H "Content-Type: application/json" \
    -d '
    {
     # paste your store properties/values here
    }'
    ```

3. The response body will confirm the request was
received. Note that the values should be the same
as you used in your **Request body**. It should
look similar to this:

    ```json
    {
    "id": "st_108",
    "name": "SliceOrder Pioneer Square",
    "address": {
        "line1": "100 S. King St.",
        "city": "Seattle",
        "state": "WA",
        "zip": "98104"
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

Cool &mdash; you added a new `store` by
sending a `POST` request.

In the future, if you'd like to make changes to a
store, see the **[Edit a store tutorial](edit-store.md)**.

If you encountered an error, refer to the
**Troubleshooting** section below.

### Related topics

- [**Get a list of all stores >**](../tutorials/get-all-stores.md)

## Troubleshooting

- **Returned a response of `>`**: make sure you included the `
at the end of the command.

- **Could not connect to server**: make sure you input your
own **server url** where noted in the command.

***
[**Tutorials**](tutorials.md) |
[**API Reference**](../../docs/index.md#api-reference-docs)
| Copyright &copy; elderains
