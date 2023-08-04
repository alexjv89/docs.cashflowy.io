---
title: Stripe
date: Last Modified 
permalink: /passthrough-api/stripe.html
eleventyNavigation:
  order: 10
  parent: passthrough-api
  key: stripe 
  title: Stripe
---
Original Stripe API docs can be found here - https://stripe.com/docs/api

## Overall options

## APIs
* In general, any object documented in the Stripe API docs should be accessible via the Cashflowy integration.

### Get something (usage example)
```
getDataFromStripe:async function(){
    console.log('>>>>>> Getting data from Stripe');
    var options = {
      method:'GET',
      url:'/v1/payouts',
      integration:INTEGRATIONS.STRIPE,
      org:ORG,
      params:{},
    }
    var result = await cf.passthrough(options)
    return result.data;
  },
```