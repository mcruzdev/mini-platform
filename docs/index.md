# Welcome 

Welcome to **mini-platform**'s home, here you will have a learning-oriented workshop with the goal to build a Platform on top of [Kubernetes](https://kubernetes.io/pt-br/) focusing on developer experience.

I got as inspiration the workshop created by [@salaboy](https://twitter.com/salaboy) called [From Monolith to Kubernetes](https://github.com/salaboy/from-monolith-to-k8s).

## Getting Started

Following this Quickstart tutorial, you will get a Platform on top of Kubernetes and know some challenges of creating one. 

### Before you begin

Before all, we need to know what we will build on this workshop:

1. We will create a command line interface (CLI) with the project [cobra](https://github.com/spf13/cobra) to allow a developer to create their applications.

**Motivation:**

Nowadays many companies want to deliver their features faster and faster. In the context of microservices in a big company, almost every day more than one microservice appears, and this microservice is initially a git repository. The developer needs to get a repo in an easy way.

**Proposal:**

The proposal here is to create a command line interface to allow the developer to create a git repository. This CLI will be called **minictl**.

