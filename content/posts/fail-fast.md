+++
date = '2025-09-17T20:56:53-04:00'
draft = true
title = 'Fail Fast, Fail Forward'
+++
# Fail Fast, Fail Forward
It's a ubiquitous mantra in modern software development. Why does it capture so much attention? Say anything that flips conventional thought on it's head and it's bound to make people stop and think. You mean failure can actually be good?

Of course the reality is quite a bit more nuanced than that. Obviously you can't go writing bad code directly on the production server in the name of developer velocity and expect it to go well. *Fail Fast, Fail Forward* only works when solid DevOps practices are in place to greatly reduce the impact of and improve time to recovery for failures. And let's not forget that "failing forward" is meant to remind us that processes should also be in place to ensure that failures always result in improvement. Ideally the same failure should never happen twice.

Let's talk about some of the DevOps practices that allow a fail fast strategy to work. This won't be an exhaustive list, but I aim to cover most of the foundational concepts.

## Infrastructure As Code (IAC)
If your important infrastructure like Kubernetes Clusters and Servers has been conjured into existance by way of "ClickOps," or in otherwords, configured directly in your cloud provider's console, you're going to have a hard time reproducing that asset quickly and accurately in the case of a catastrophic failure. Terraform and Ansible among others are fantastic tools which allow you to write code which defines your infrastructure. Just like any other code it can be checked into version control, allowing you to quickly revert the state of an asset to a previous point in time, or even redeploy critical infrastructure to a new region if one of your cloud provider's datacenters goes down (which definitely never happens).

## Continuous Integration
Possibly the most talked about concept in DevOps is CI/CD, of which the first step is Continuous Integration. It's not so much about fast recovery from failure as it is preventing mistakes in the first place. CI is automation that takes your code from commit to artifact. It should run your tests, lint, compile, build, and theoretically catch most code problems before they get deployed. Continuous Integration is also about fast developer feedback cycles, also know as "left shift testing." If failures here are silent or obscured amongst walls of terminal logs, it's not helping developers fail fast. The idea is to make code problems known as quickly as possible, so that developers can keep developing, rather than stare at a pipeline wondering why it didn't work.

## Continuous Deployment
The other side of CI/CD is Continuous Deployment. This is automation that takes code from artifact to running on infrastructure, that may mean not only deploying the application, but application dependencies as well, databases, cashes, networking, and so on.


*This article is a work in progress*
