---
title: spreadsheet.values.update
date: Last Modified 
permalink: /passthrough-api/google-sheets/spreadsheet.values.update.html
eleventyNavigation:
  order: 10
  parent: google-sheets
  key: spreadsheet-values-update
  title: spreadsheet.values.update
---
Use this to update values from an existing google sheet. You need to specify
- google sheet id (spreadsheet_id)
- range 

Range can be
- Sheet - whole sheet
- Sheet!A:A - column
- Sheet!1:1 - row
- Sheet!A1:Z10 - specific set of cells

Original API docs - https://developers.google.com/sheets/api/reference/rest/v4/spreadsheets.values/update

values has to be 2 by 2 matrix containing data such as `[["alex","alex2"],["alex3","alex4"]]`.
### Cashflowy Usage
``` js
var range = `raw!1:1000`;
var options = {
  method:'PUT',
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
