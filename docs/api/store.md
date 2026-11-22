---
# markdownlint-disable
# vale off
# tags used by just-the-docs theme
layout: default
nav_order: 3
has_children: true
# tags used by AI files
description: Information about the `store` resource
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
    - /docs/get-stores
    - /docs/add-store
examples: []
api_endpoints: 
    - /stores
version: "v1.0"
last_updated: "2026-11-21"
# vale  on
# markdownlint-enable
---

# `store` resource

Base endpoint:

```shell
{server_url}/stores
```

Contains information about the `stores` of the API.

A store resource contains location, hours, and delivery
information about stores in the pizza business.

Before you can create a `menu` or `order` resource in the service,
you must create a `store` resource to assign to the `menu` or `order`.

Learn more about the [menus](#store-resource) *(coming soon)* and [orders](#store-resource) *(coming soon)* resources.

## Resource properties

Example `store` resource

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
      "delivery_fee": 2.0,
      "hours": {
        "open": "11:00",
        "close": "22:00"
      },
      "timezone": "America/Los_Angeles",
      "open_now": true
    }
```

| Property name | Type | Description |
| ------------- | ----------- | ----------- |
| `id` | number | The store's unique record ID |
| `name` | string | The store name |
| `address` | object | Object containing store address details |
| `line1` | string | The store's street address |
| `city` | string | The city where the store is located |
| `state` | string | The state the store is located |
| `zip` | number | The zip code where the store is located |
| `order_types` | array | Array containing items `pickup` or `delivery` |
| `delivery_fee` | number | Fee for `order_type`:`delivery` |
| `hours` | object | Object containing store open and close times today |
| `open` | string | Store's local opening time in 00:00 24-hour time format |
| `closed` | string | Store's local closing time in 00:00 24-hour time format |
| `timezone` | string | Store timezone |
| `open_now` | boolean | Whether the store is currently open based on store local time |

## Read operations

* [Get all stores](get-all-stores.md) *(coming soon)*
* [Get store by ID](get-store.md)

## Create operations

* [Create store](create-store.md) *(coming soon)*

## Edit operations

* [Edit store](edit-store.md) *(coming soon)*

## Delete operations

* [Deletes](delete-store.md) *(coming soon)*
