---
title: Passthrough API
date: Last Modified 
permalink: /passthrough-api-deprecated.html
eleventyNavigation:
  key: passthrough-api-deprecated
---

A typical company's financial process consists of many repetative processes. When these process are done manually they result in keystroke errors, delays and frustrations for upper management. Cashflowy platform helps you automate some of your companies financial processes. asdf asdf

You can use the cashflowy platform for
- preparing reports
- enforcing control

asdfasdf
The platform consists of:
1) Passthrough API
2) Job runner

Head up: You will need some basic scripting knowledge to work with cashflowy platform. 

### Passthrough API
A company uses multiple tools in its financial process. One tool for all financial process is hard to achieve and even if you achieve it, it can make your company very rigid. So inevitablity a company has multiple tools for various parts of finacial systems such as stripe, braintree for collections or payouts, mercury for banking, chargebee for recurring subscriptions, quickbooks, SAP for book keeping etc. 

Some of these tools have native integrations with each other. Sometimes these native integrations are build for specific usecases. Most often these tools also have APIs. However the problem is if you are writing integrations between these tools, you will need to think of implementation logic(authentication, autherization etc) along with business logic. 

Passthrough APIs take care of implementation logic for you, so that when you are writing scripts, you can focus on business logic alone. This makes your code simple and clean. This allows you to:
- write integrations faster
- maintain/upgrade integrations easier

Additionally since passthrough hands authentications, you are not sharing API keys and credentials of various tools with developers. You are sharing cashflowy API keys, with which you can control what tools can be accessed. 

### Job runner
Once you write your script, you need a place to execute these scripts. You can do that with cashflowy Job runner. 



