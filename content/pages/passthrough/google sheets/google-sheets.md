---
title: Google sheets
date: Last Modified 
permalink: /passthrough-api/google-sheets/index.html
eleventyNavigation:
  order: 10
  parent: passthrough-api
  key: google-sheets 
  title: Google sheets
---
Original Google sheets docs can be found here - https://developers.google.com/sheets/api/reference/rest

Integration to Google Sheets is done via Google Cloud Service Accounts. 
When an org is created on app.cashflowy.io, we also create a "Service Account" for that org.
This Service Account is then integrated with the Cashflowy org.
There on, the Cashflowy Passthrough API can read and write to Google Sheets. (The sheets should be "shared" with the Service Account email address with "Editor" access.)

The advantage of the Service Account method over OAuth is the ability for strong version control. 
Whenever a script modifies the sheet, that activity will get logged in the name of the service account and a new version will get created. This serves as an audit trail, and also helps with backup and troubleshooting.

## Overall options

## APIs

### Get something

