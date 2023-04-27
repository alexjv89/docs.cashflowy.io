---
title: Get Chart of Accounts from Zoho Books API
date: Last Modified 
permalink: /passthrough-api/zoho-books/get-chart-of-accounts.html
eleventyNavigation:
  order: 10
  parent: zoho-books
  key: get-chart-of-accounts
  title: Get Chart of Accounts
---

Original API docs - https://www.zoho.com/books/api/v3/chart-of-accounts/#list-chart-of-accounts

### Cashflowy Usage
``` js
var options = {
			method:'GET',
			url:'/chartofaccounts',
			integration:INTEGRATIONS.ZOHO_BOOKS,
			org:ORG,
			params:{
				filter_by:'AccountType.All'
			},
		}
		var result = await cf.passthrough(options)
```