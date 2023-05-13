# Introduction
This is the first step on the journey to create a Platform on top of Kubernetes.

In this step we will create a Command Line Interface (CLI) focusing on the developer experience.

## Platform on MeLi

Today, I am a Software Enginner at [Mercado Livre (MeLi)](https://www.linkedin.com/company/mercadolivre-com/mycompany/) and I am responsible for creating toolings for developers, such as Documentation Platform and Performance Test Platform. 

Working on MeLi, when I want to create an application (service, microservice, etc.), I just tell to Fury (interface web) to create for me, and after seconds I have a Git repository, dashboards for Observability, etc.

## I as developer wants a way to easily get a Github repository

**Motivation:**

Nowadays many companies want to deliver their features faster and faster. In the context of microservices in a big company, almost every day more than one microservice appears, and this microservice is initially a git repository. The developer needs to get a repo in an easy way.

**Thoughts**

I thought to create a web interface with NextJS or just React, but as I still have problems with overengineering, I was going to try to make the frontend as beautiful as possible. So decides to create a CLI that does this for me.

I decided to create a command line interface (CLI) with the project [cobra](https://github.com/spf13/cobra).


**Proposal:**

The proposal here is to create a command line interface to allow the developer to create a git repository. This CLI will be called **minictl**.

The minictl repository can be found [here](https://github.com/mcruzdev/minictl) and the step-by-step for creating it is [here](http://127.0.0.1:8000/CLI/creating-minictl/).

## Implementation

I documented on following pages, some step-by-step to create a CLI to communicate with Github creating a repository:

- [Creating the minictl CLI](./creating-minictl/index.md)
- [Creating the Github repository](./creating-github-repository/index.md)

Enjoy it, learn and thank you!
