---
title: CLI Arguments to be added in scripts
date: Last Modified 
permalink: /cli-arguments/index.html
eleventyNavigation:
  order: 100
  key: cli-arguments
  title: CLI Arguments in Scripts
---
### CLI Arguments for Atomic scripts
| **name**     | **type** | **Zoho Books** | **Quickbooks** |
|--------------|----------|----------------|----------------|
| account_id   | String   | Yes            |                |
| account_name | String   | Yes            |                |
| start_date   | String   | Yes            |                |
| end_date     | String   | Yes            |                |
| sheet_id     | String   | Yes            |                |
| sheet_name   | String   | Yes            |                |


#### Cashflowy Node SDK usage
```js
var commandLineArgs = require('command-line-args');
const optionDefinitions = [
	{ name: 'account_id', type: String },
	{ name: 'account_name', type: String },
	{ name: 'start_date', type: String },
	{ name: 'end_date', type: String },
	{ name: 'sheet_id', type: String },
	{ name: 'sheet_name', type: String },
];
const cli_args = commandLineArgs(optionDefinitions);
```
---
### CLI Arguments for Scheduler/Queueing scripts (scripts that trigger/refer to atomic scripts)
| **name**   | **type** | **Zoho Books** | **Quickbooks** |
|------------|----------|----------------|----------------|
| start_date | String   | Yes            |                |
| end_date   | String   | Yes            |                |
| skip       | Number   | Yes            |                |


#### Cashflowy Node SDK usage
```js
var commandLineArgs = require('command-line-args');
const optionDefinitions = [
	{ name: 'start_date', type: String },
	{ name: 'end_date', type: String },
	{ name: 'skip', type: Number },
];
const cli_args = commandLineArgs(optionDefinitions);
```
