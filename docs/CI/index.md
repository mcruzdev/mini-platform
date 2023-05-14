# Continuos Integration

Today is very easy to run a Continuous Integration pipeline, if you use Github you can use Github Actions,
if you use Gitlab, you can use Gitlab CI, etc.

## I as developer wants a way to easily create a runnable docker image for deploying

**Thougts**:

The main goal here is to construct a Platform on top of Kubernetes, reading the[ Platform Engineering on Top of Kubernetes book](https://www.manning.com/books/platform-engineering-on-kubernetes), mentioned on the [main page](../index.md) is possible to see two options to run a Continuous Integration pipeline on Kubernetes: [Tekton](https://tekton.dev/) and [JenkinsX](https://jenkins-x.io/).

I will not detail each one, I prefer now to use the more simple now.

A developer can use some languages to create an (micro)service, then we can use one pipeline for technology and application type, I will consider only web applications where we can have a server running
on specified port.

**Proposal**:

**How the pipeline will start?**

I want to execute the pipeline from a webhook (a request from `minictl` CLI).

**Which programming languages my Continuous Integration will support?**

I want to create a generic pipeline using [Paketo Builpacks](https://paketo.io/docs/) where is possible to detect which technology the github repository had and create a Docker image for me.

Let's go, thank you for reading!