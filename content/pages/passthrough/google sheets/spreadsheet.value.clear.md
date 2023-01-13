---
title: spreadsheet.values.clear
date: Last Modified 
permalink: /passthrough-api/google-sheets/spreadsheet.values.clear.html
eleventyNavigation:
  order: 10
  parent: google-sheets
  key: spreadsheet-values-clear
  title: spreadsheet.values.clear
---
Use this to update values from an existing google sheet. You need to specify
- google sheet id (spreadsheet_id)
- range 

Range can be
- Sheet - whole sheet
- Sheet!A:A - column
- Sheet!1:1 - row
- Sheet!A1:Z10 - specific set of cells

Original API docs - https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/clear

### Cashflowy Usage
``` js
var range = `raw!1:1000`;
var options = {
  method:'PUT',
  url:`/v4/spreadsheets/${sheet_id}/values/${range}:clear`,
  integration:27,
  org:25,
}
var data = await cf.passthrough(options)
```
