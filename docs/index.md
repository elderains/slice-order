---
# markdownlint-disable
# vale off
# tags used by just-the-docs theme
layout: default
nav_order: 1
# tags used by AI files
description: Describes the SliceOrder API for a new user
topic_type: overview
tags: 
    - introduction
categories: 
    - tutorial
ai_relevance: high
importance: 9
prerequisites: []
related_pages: 
    - /quickstart 
    - /api/index
    - /tutorials/get-store
examples: []
api_endpoints: []
version: "v1.0"
last_updated: "2026-11-19"
# vale  on
# markdownlint-enable
---

# SliceOrder API

## Overview

SliceOrder is a REST API that manages orders for a pizza
franchise.

Features include:

* store and address lookup
* menu management by store
* topping management
* create orders and order lookup
* webhook events to notify store of order status changes

## Get started

Wondering where to begin? [Look up a menu using our SliceOrder quickstart guide](/quickstart.md) to see how easy it is to use!

## Documentation

Looking for more information? Learn more here:

* [Quickstart guide](quickstart.md)
* [Tutorials](/tutorials/index.md)
* [API Reference](../api/index.md)

## Tutorials

Learn how to do common tasks with SliceOrder.

First, complete the [quickstart guide](quickstart.md).
You only have to do this one time per development system.

After your system is ready, head to the [Tutorials](/tutorials/index.md) to learn more.

## API reference docs

The API reference docs refer to a `{base_url}` when they
refer to the URL of a resource. The `{base_url}` value depends
on the installation of the service.

When run locally for testing, the `{base_url}` is
generally `http://localhost:3000`.

SliceOrder includes five primary resources:

| Resource | Description |
| --- | --- |
| `stores` | Stores and store locations |
| `menus` | Menus available by store |
| `toppings` | Available pizza toppings |
| `orders` | Orders include status, store, pizza details, and more |
| `webhook_endpoints` | Webhooks allow for automatic updates on order status |
