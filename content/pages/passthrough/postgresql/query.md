---
title: Make a query
date: Last Modified 
permalink: /passthrough-api/postgresql/query.html
eleventyNavigation:
  order: 10
  parent: postgresql
  key: query
  title: Make a query
---

### Cashflowy Usage
``` js
var options = {
      method:'POST',
      integration:22,
      org:22,
      params:{},
      data:{
        query:'select * from job_job;',
        // escape_values:[]
      }
    }
var data = await cf.passthrough(options)
```


Note: 
- options.url is not needed
- data.escape_values is an array containing values to escape in case query is parameterized. This is optional. 