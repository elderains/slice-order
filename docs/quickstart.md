---
# markdownlint-disable
# vale off

layout: default
nav_order: 2
description: SliceOrder Quickstart
topic_type: overview
# test:
#   test_apps:
#     - json-server@0.17.4
#   server_url: localhost:3000
#   local_database: /api/pizzaSlicedb.json
#   testable:
#     - GET example / 200
#     - POST example / 201
# vale  on
# markdownlint-enable
---

# SliceOrder API Quickstart

<!-- vale Google.Acronyms = off -->
## It's Pizza Time

Welcome to SliceOrder, a cloud-hosted order management tool for
your pizza business.

[**Start a Tutorial**](/tutorials/index.md) |
[**API Reference**](../api/index.md)

### Keep track of your orders

Manage incoming orders and maintain a log of past orders to
inform sales and inventory data.

### Manage menus

Customers love variety, and menu management is easy with
SliceOrder. Each store location can have its own custom menu.

### Notifications for order status changes

SliceOrder utilizes webhooks to auto-update each order
status when it changes -- no need to submit a new request
to check the status.

## Prerequisites

Below are the steps required before you can start
the tutorials for **SliceOrder**. Expect this
preparation to take about 20 minutes to complete.

To complete the tutorials in this section, you need the following:

<!-- vale Google.Acronyms = NO -->

* Background in REST API functionality.
* A [GitHub account](https://github.com).
* Fork this repository, or otherwise obtain a current copy
of
[api/pizzaSlicedb.json](../api/pizzaSlicedb.json).
* Version 0.17.4 of [json-server](https://www.npmjs.com/package/json-server/v/0.17.4).
* A **terminal to run curl** or the **[Postman desktop app](https://www.postman.com/downloads/)**.
        Because you run the **SliceOrder** on your development system with an `http://localhost`
        host name, the web-version of Postman can't perform the exercises.

<!-- vale Google.Acronyms = YES -->

## Test your development system

To test your development system:

1. Create and checkout a test branch of your fork of the `slice-order` repository.

    ```shell
    cd <your GitHub repository workspace>
    ls
    cd slice-order
    ## create a new branch
    git checkout -b tutorial-test
    cd api
    json-server -w pizzaSlicedb.json
    ```

    If you installed the software correctly, you should see
    the service start and display the URL of the service: `http://localhost:3000`.

2. Make a test call to the service.

    ```shell
    curl http://localhost:3000/orders
    ```

3. If the service is running correctly, you should see a list of orders from the app,
    such as in this example.

    ```json
     {
      "id": "ord_8f3a21",
      "order_id": "ord_8f3a21",
      "status": "received",
      "store_id": "st_104",
      "type": "delivery",
      "items": [
        {
          "sku": "margherita",
          "size": "large",
          "qty": 1,
          "toppings": [],
          "line_total": 12.5
        }
      ],
      "subtotal": 12.5,
      "delivery_fee": 2.0,
      "total": 14.5,
      "eta_minutes": 35,
      "scheduled_for": null,
      "created_at": "2026-11-10T19:42:10Z"
    },
    {
      "id": "ord_2c7d90",
      "order_id": "ord_2c7d90",
      "status": "preparing",
      "store_id": "st_102",
      "type": "pickup",
      "items": [
        {
          "sku": "build_your_own",
          "size": "medium",
          "qty": 2,
          "toppings": [
            "mushrooms",
            "extra_cheese"
          ],
          "line_total": 25.5
        }
      ],
      "subtotal": 25.5,
      "delivery_fee": 0.0,
      "total": 25.5,
      "eta_minutes": 20,
      "scheduled_for": null,
      "created_at": "2026-11-10T19:15:30Z"
     },
        ...
    ```

### Troubleshooting

If you received an error, one of the following common causes
is likely:

1. A typo in a command.
2. You aren't in the correct directory.
3. A required software component didn't install correctly.
4. A required software component isn't up to date.

### Success

If you see the list of orders from the service, you're ready
to start using SliceOrder:

**[Look up a store >](/tutorials/get-store.md)**

***

[**Tutorials**](/tutorials/index.md) |
[**API Reference**](../api/index.md)
| Copyright &copy; elderains
