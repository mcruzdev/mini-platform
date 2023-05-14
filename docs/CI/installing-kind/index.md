# Introduction

I do not want to 

## KinD - Kubernetes in Docker

What is KinD?

> kind is a tool for running local Kubernetes clusters using Docker container “nodes”.
> kind was primarily designed for testing Kubernetes itself, but may be used for local development or CI.

To proceed with the steps outlined, it is necessary to [install KinD (Kubernetes in Docker)](https://kind.sigs.k8s.io/docs/user/quick-start/#installation).

## Installing Tekton

In this step, I will demonstrate the installation of Tekton on a KinD cluster. There are multiple methods available for installing Tekton into a cluster, but for this demonstration, I will use Helm as my preferred approach.

```sh
    helm repo add cdf https://cdfoundation.github.io/tekton-helm-chart/
    helm repo update
    helm install tekton cdf/tekton-pipeline
```

Please note that this step is not performed by the developer. The developer does not need to be concerned with configuring pipelines; they simply need to utilize it using the minictl CLI.

### Installing Tekton Dashboard

https://tekton.dev/docs/dashboard/install/

### Installing tkn CLI

https://tekton.dev/docs/cli/

### Installing git-clone and buildpacks

https://hub.tekton.dev/