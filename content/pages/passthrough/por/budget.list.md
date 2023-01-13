---
title: budget.list
date: Last Modified 
permalink: /passthrough-api/google-sheets/budget.list.html
eleventyNavigation:
  order: 10
  parent: por
  key: budget-list
  title: budget.list
---
List budgets

Original API docs - https://documenter.getpostman.com/view/21786821/2s8YzWT1eM#830462df-06e0-4940-b58f-bf8ea7006e89

### Cashflowy Usage
``` js
var options = {
  method:'GET',
  url:`/apis/v1/por_budgets`,
  integration:27,
  org:11,
  params:{},
}
var data = await cf.passthrough(options)
```
