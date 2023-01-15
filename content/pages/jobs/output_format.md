---
title: Jobs Output format
date: Last Modified 
permalink: /jobs/output_format.html
eleventyNavigation:
  order: 10
  parent: jobs
  key: jobs_output_format
  title: Jobs output format
---
For the cashflowy job runner to know status of execution of the job, it expects the job to output a string to console after execution of the job. 

example:
```
cf_output::{"success":0,"warning":0,"failure":0}
```

This should be last line printed to the console by the script. Cashflowy will additionally only process the last line if it starts with `cf_output::` followed by a stringified JSON object. 

The stringified json object has different structure for maker jobs and checker jobs.

### Maker jobs output structure

| Field | Description | Required |
|----|----|----|
| success | Count of objects successfully processed | yes |
| warning | Count of objects processed with a warning.  | yes |
| failure | Count of objects that could not be processed in this job execution.  | yes |

### Check jobs output structure

| Field | Description | Required |
|----|----|----|
| status | Can be `success` , `warning` or `failure` . | Yes |
| comments | The code can enter any details associated with the run here.  | No |
