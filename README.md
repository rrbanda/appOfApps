# Composer AI Gitops
# AppOfApps Repository

## Structure Overview
- **Subdirectories**:
  - `appOfApps`: Contains the root manifest for deploying other applications or services.
  - `chatbot`: Represents an individual application or microservice.
  - `data-ingestion`: Represents another application or microservice focused on data ingestion.
  - `util`: Likely includes helper scripts or utilities for deployment automation or shared configurations.
- **Files**:
  - `README.md`: Documentation to guide usage and structure.
  - `.gitignore`: Excludes unnecessary files during Git operations.

## Usage in ArgoCD and OpenShift
- **AppOfApps Pattern**:
  - The repository organizes deployment manifests hierarchically.
  - Enables managing multiple applications through a single parent manifest using ArgoCD.
- **Benefits**:
  - Modular design for deploying and managing OpenShift applications.
  - Scalable workflows suited for microservice-based architecture.


## Description

GitOps repository responsible for installing components used for Composer AI

## Installation

### Prerequisites

- Requires OpenShift cluster of version 4.16 or above

### Install Cluster Level Components (Recommended)

Using the `bootstrap` script located in the [Cluster Gitops](https://github.com/redhat-composer-ai/cluster-gitops) repository will install all the required components as well as all the Composer AI Components located in this repository.

### Install Directly

If you already have an existing cluster that contains all the required cluster level operators the application can be installed by installing the helm chart located in `appOfApps`:

```sh
helm install composerAiConfig ./appOfApps
```

> [!NOTE]  
> Change `clusterDomain` and `repo` information in the `values.yaml` file if required.
