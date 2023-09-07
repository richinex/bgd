# BGD Application for Kubernetes

This repository contains Kubernetes resources to deploy the `bgd` application.

## Application Overview

- **ArgoCD Application**: This serves as the configuration to deploy the `bgd` app using ArgoCD.
- **Kubernetes Deployment**: Deploys the `bgd` app into the `bgd` namespace.

### ArgoCD Application

The application's definition outlines the deployment process through ArgoCD:

- **Destination Cluster**: The default Kubernetes service
- **Namespace**: `bgd`
- **Source Repository**: [https://github.com/richinex/bgd.git](https://github.com/richinex/bgd.git)
- **Path in Repo**: `resources`
- **Git Branch**: `master`
- **Sync Policy**: Automated with `prune` and `selfHeal` enabled.

### BGD Kubernetes Deployment

Details of the deployment:

- **Namespace**: `bgd`
- **Replicas**: 1
- **Container Image**: `quay.io/rhdevelopers/bgd:1.0.0`
- **Environment Variable (COLOR)**: The application color set to `blue`.

## Deployment

To deploy the application, make sure you have ArgoCD set up in your cluster and use it to apply the `Application` resource. This will automatically deploy the `bgd` app based on the defined configurations.
```
k apply -f bgd-app.yaml
```
---

**Note**: Ensure necessary configurations and prerequisites are met before deployment.
