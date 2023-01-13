---
title: spreadsheet.values.append
date: Last Modified 
permalink: /passthrough-api/google-sheets/spreadsheet.values.append.html
eleventyNavigation:
  order: 10
  parent: google-sheets
  key: spreadsheet-values-append
  title: spreadsheet.values.append
---
Use this to update values from an existing google sheet. You need to specify
- google sheet id (spreadsheet_id)
- range 

Range can be
- Sheet - whole sheet
- Sheet!A:A - column
- Sheet!1:1 - row
- Sheet!A1:Z10 - specific set of cells

Original API docs - https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/append

### Cashflowy Usage
``` js
var range = `raw!1:1000`;
var options = {
  method:'POST',
  url:`/v4/spreadsheets/${gsheet_id}/values/${range}`,
  integration:27,
  org:25,
  params:{
    valueInputOption:'USER_ENTERED'
  },
  data:{
    "majorDimension": "ROWS",
    "values": values
  }
}
var data = await cf.passthrough(options)
```
