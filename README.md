# Qubership Kube Event Generator

This document provides information for developers to start working with k8s-event-generator
and implementing features and fixing issues.

## Table of Content

* [Qubership Kube Event Generator](#qubership-kube-event-generator)
  * [Table of Content](#table-of-content)
  * [Repository structure](#repository-structure)
  * [How to start](#how-to-start)
    * [Deploy](#deploy)
      * [Deploy with helm](#deploy-with-helm)
    * [How to debug](#how-to-debug)
    * [How to troubleshoot](#how-to-troubleshoot)
  * [CI/CD](#cicd)
  * [Evergreen strategy](#evergreen-strategy)

## Repository structure

* `./manifests` - kubernetes manifests for manual deploy
* `./main.go` - application entrypoint

Files for build:

* `./Dockerfile` - to build Docker image

## How to start

### Deploy

This microservice can be deployed manually with `kubectl` or `oc` cli tool.

1. Login to cloud and set context.

2. Modify manifests. At least you need to set Docker image of the service.

3. Run command to install k8s-event-generator:

```bash
kubectl apply -f ./manifests
```

To uninstall deployment you need to delete manually all the manifests.

#### Deploy with helm

Not applicable.

### How to debug

You can debug k8s-event-generator locally with default or custom parameters in your IDE.
The only thing that you need to do before run/debug service locally you need to login and set context to the cloud.
k8s-event-generator requires connection to cloud to create Kubernetes events.

### How to troubleshoot

There are no well-defined rules for troubleshooting, as each task is unique, but there are some tips that can do:

* See deployment parameters and cli flags
* See logs of the service

## CI/CD

There is no CI/CD pipeline.

## Evergreen strategy

To keep the component up to date, the following activities should be performed regularly:

* Vulnerabilities fixing, dependencies update
* Bug-fixing, improvement and feature implementation
