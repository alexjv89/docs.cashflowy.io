---
title: por.list
date: Last Modified 
permalink: /passthrough-api/google-sheets/por.list.html
eleventyNavigation:
  order: 10
  parent: por
  key: por-list
  title: por.list
---
List PORs

Original API docs - https://documenter.getpostman.com/view/21786821/2s8YzWT1eM#42c04d95-278d-46d4-a2df-9ce51f9109b6

### Cashflowy Usage
``` js
var options = {
  method:'GET',
  url:`/apis/v1/por_purchase_order_requests`,
  integration:27,
  org:11,
  params:{},
}
var data = await cf.passthrough(options)
```
