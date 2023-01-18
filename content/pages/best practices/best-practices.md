---
title: Best practices
date: Last Modified 
permalink: /best-practices.html
eleventyNavigation:
  order: 10
  key: best-practices 
  title: Best practices
---

Here are some best pratices for organising scripts and jobs. 


### 1. Atomic jobs - One script does one specific job
You can write scripts that does multiple things in the same script. For example you script can update 3 sheets and 3 scripts can update one sheet. Cashflowy APIs provide you that flexibility. That said, it recommended to focus on one task in one script/job. This way your scripts becomes resilient during execution. If something breaks in between (and it will break eventually. Always assume your logic will break under some unknown new scenario that you have not considered), atomic tasks are easier to repair. The more complex a script becomes, the harder it is for you to fix it. 

So 3 scripts updating one sheet is generally better than 1 script updating 3 sheets. Then the question is how big should a task be? That is subjective. Any task can be broken down into smaller and smaller tasks. Atomic tasks are just a mental model. Break it down enough so that you can wrap you head around the business logic. 


### 2. Same folder struture as groups
Scripts are stored in folders. You can use nested folders to organise scripts. Typically one job is executing one script. Keeping it one to one is necessary but might be better for organising your automations. Jobs can be grouped on cashflowy platform. Group can be nested as well. It is recommended to organise your code in the same nested structure that you specify in groups. This way it is easier for you to find and modify your jobs. 

