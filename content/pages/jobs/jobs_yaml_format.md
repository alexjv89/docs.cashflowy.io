---
title: Jobs definition format
date: Last Modified 
permalink: /jobs/yaml_format.html
eleventyNavigation:
  order: 10
  parent: jobs
  key: jobs_yaml_format
  title: Jobs definition format
---

## Sample job definition
```yaml
- name: Append transactions
  rd_id: 89462c62-b536-414a-b700-497ae45000da
  description: Append transactions to the respective budget sheet
  group: Maker/Cashflow report
  executionEnabled: true
  scheduleEnabled: true
  options:
  - name: ENCRYPTION_PASSWORD
    secure: true
    storagePath: keys/ENCRYPTION_PASSWORD
    valueExposed: true
  - name: type1
    required: true
    value: R&x
  - name: sheet_id
    required: true
    value: 1amSMeyYWtQL_QQwjoXiKqTtQDwRSkw04KGkYipNPF8E
  - name: type2
    required: true
    value: BMS
  schedule:
    month: '*'
    hour: '*'
    minute: 0/25
    seconds: '0'
    weekday: '*'
    year: '*'
  sequence:
    commands:
    - script: |-
        cd scripts/rundeck-jobs
        pwd
        node lib/aes.js decrypt ./clients/exponent/env/cf_app.env.js.enc @option.ENCRYPTION_PASSWORD@
        node clients/exponent/scripts/maker/prepare\ financial\ report/append_transactions.js  --type1 @option.type1@ --type2 @option.type2@ --sheet_id @option.sheet_id@
```

## YAML objects
| Fields | Description | Required |
|----|----|----|
| name | Name of the job. This is will be visible in the UI | yes |
| rd_id | Unique id of the job. This is auto generated. Id is required if you want to update an existing job.  | required for update requests |
| description | Write description of the job here for others to understand this job better | optional |
| group | Organise jobs into groups. Groups can be nested. Nested groups are separated by `/` | optional |
| executionEnabled | Can be `true` or `false`. Set this to false to prevent users from executing this job. Scheduled execution also will be stopped when set to false | yes |
| scheduleEnabled | Can be `true` or `false`. Set this to false to disable scheduled execution.  | yes |
| options | Set variables for the job. Refer to `options` object for its documentation.  | optional |
| schedule | Define the schedule for running this job. Refer to `schedule` object for its documentation | required if `scheduleEnabled` = true |
| sequence | Define the set of commands that this job will run. Sequence has one sub object - `commands` . Commands accept an array of `script` .  | yes |


### Options

| Fields | Description | Required? |
|----|----|----|
| name | Name of the variable | yes |
| required | Can be `true` or `false` . | yes |
| value | Default value if not specified by user | yes |

### Schedule

| Fields | Description | Required? |
|----|----|----|
| month | select months to execute this job | yes |
| hour | select hours | yes |
| minute | select minutes | yes |
| seconds | select seconds  | yes |
| weekday | select which weekday to execute this. | no |
| year | select which year to execute this.  | yes |
| cron | Enter the value as a cron string (not supported yet) | no |
