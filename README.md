# Kubernetes Projects Initializer Tutorial

This tutorial walks you through building and deploying a [Kubernetes Initializer](https://kubernetes.io/docs/admin/extensible-admission-controllers/#what-are-initializers) that helps provision namespaces and grant access to users.

> Initializers are an alpha feature and subject to change. Please report any Initializer specific issues on the [Kubernetes issue tracker](https://github.com/kubernetes/kubernetes/issues).

## Prerequisites

Kubernetes 1.7.0+ is required with [support for Initializers enabled](https://kubernetes.io/docs/admin/extensible-admission-controllers/#enable-initializers-alpha-feature). If you're using Google Container Engine create an alpha cluster:

```shell
gcloud alpha container clusters create k0 \
  --enable-kubernetes-alpha \
  --cluster-version 1.7.0
```

If you're using minikube 0.27+, activate `admissionregistration.k8s.io/v1alpha1` on runtime-config:

```shell
minikube start --extra-config=apiserver.runtime-config=admissionregistration.k8s.io/v1alpha1
```

Download the tutorial by cloning this repository:

```shell
git clone TBD
```

```shell
cd kubernetes-projects-initializer-tutorial
```

## Tutorial

- [Configure RBAC](docs/01.configure-rbac.md)
- [Create Projects Custom Resource](docs/02.create-projects-custom-resource.md)
- [Deploy The Project Initializer](docs/03.deploy-project-initializer.md)
- [Initializing Deployments](docs/04.initializing-deployments.md)
- [Cleaning Up](docs/05.cleanup.md)
