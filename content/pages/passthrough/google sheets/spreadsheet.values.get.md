---
title: spreadsheet.values.get
date: Last Modified 
permalink: /passthrough-api/google-sheets/spreadsheet.values.get.html
eleventyNavigation:
  order: 10
  parent: google-sheets
  key: spreadsheet-values-get
  title: spreadsheet.values.get
---
Use this to get values from an existing google sheet. You need to specify
- google sheet id (spreadsheet_id)
- range 

Range can be
- Sheet - whole sheet
- Sheet!A:A - column
- Sheet!1:1 - row
- Sheet!A1:Z10 - specific set of cells

Original API docs - https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/get

### Cashflowy Usage
``` js
var options = {
  method:'GET',
  url:`/v4/spreadsheets/${spreadsheet_id}/values/${range}`,
  integration:27,
  org:25,
  params:{},
}
var result = await cf.passthrough(options)
```
