---
title: Get all transactions from one specific account via Zoho Books API
date: Last Modified 
permalink: /passthrough-api/zoho-books/get-all-transactions-from-one-account.html
eleventyNavigation:
  order: 20
  parent: zoho-books
  key: get-all-transactions-from-one-account
  title: Get all transactions from one account
---

Original API docs - https://www.zoho.com/books/api/v3/chart-of-accounts/#list-chart-of-accounts

### Cashflowy Usage
``` js
var options = {
	method:'GET',
	url:'/chartofaccounts/transactions',
	integration:INTEGRATIONS.ZOHO_BOOKS,
	org:ORG,
	params:{
		account_id:cli_args.account_id,
		"date_start":cli_args.start_date,
		per_page:5000,
	},
}
var result = await cf.passthrough(options)
```