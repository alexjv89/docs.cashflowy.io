---
title: Passthrough API
date: Last Modified 
permalink: /passthrough-api.html
eleventyNavigation:
  order: 5
  key: passthrough-api
  title: Passthrough API
---
Passthrough API is a feature of the Cashflowy platform.

It provides a way for developers to write scripts that read and write data from/to third-party tools without having to manage authentication with the third-party tools.

This is possible because Cashflowy has integrations with third-party tools, and these integrations handle all the authentication logic and complexity.

For scripting, Passthrough API is best used/accessed using the **Cashflowy Node SDK**. The SDK is essentially a wrapper on top of the Passthrough API.
The docs of specific Passthrough API endpoints have examples of how to use it via the SDK. Look for the `Cashflowy usage` heading.
* Eg. 1 - [Get Chart of Accounts from Zoho Books](https://docs.cashflowy.io/passthrough-api/zoho-books/get-chart-of-accounts.html)
* Eg. 2 - [Get all transactions from one specific account via Zoho Books API](https://docs.cashflowy.io/passthrough-api/zoho-books/get-all-transactions-from-one-account.html)

## Anatomy of Passthrough API

Applicable for GET/PUT/POST requests.

### Required Headers
| **Header Key Name** | **Header Key Value** |
|---------------------|-----------------------|
| api-key             | `api-key`           |
| api-secret          | `api-secret`        |

### Required Parameters
| **Parameter**  | **Parameter value**                                                              |
|----------------|----------------------------------------------------------------------------------|
| url            | `third-party API endpoint, without the third-party base url`                  |
| org_id         | `org_id of the Cashflowy org/account`                                          |
| integration_id | `integration_id of the org's integration with the particular third-party tool` |
---
## Example illustrating the anatomy of a Passthrough API endpoint
`https://app.cashflowy.io/passthrough?url=/banktransactions&org_id=36&integration_id=9` is the passthrough API URL to GET/PUT/POST
* Bank transactions present in the Zoho Books account (`/banktransactions` -is the official Zoho Books endpoint for the `Bank transactions` Zoho Books object [as mentioned in the Zoho Books API](https://www.zoho.com/books/api/v3/bank-transactions/#overview)) 
* of the client whose Cashflowy org id = `36`.
* This becomes possible because the Cashflowy org `36` has already set up a `zoho_books` integration, and the id of that integration is `9`

#### Notes
1. If a Cashflowy org does not have an integration of type `zoho_books` set up in their account, the Passthrough API request shown in the above example will fail. 
2. That is, a working integration between the org's Cashflowy account and their account on the third-party tool is a dependency for Passthrough API to work.