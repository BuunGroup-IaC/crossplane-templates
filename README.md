# Crossplane Templates for IDP

This repository contains Crossplane V2 compositions and XRDs for the Internal Developer Platform.

## Structure

```
├── setup/                    # Cluster setup resources
│   ├── provider-kubernetes.yaml
│   └── functions.yaml
├── xrds/                     # Composite Resource Definitions
│   └── workspace.yaml
├── compositions/             # Compositions
│   └── workspace.yaml
└── examples/                 # Example XR instances
    └── workspace-example.yaml
```

## Installation

1. Install the Kubernetes provider and functions:
   ```bash
   kubectl apply -f setup/
   ```

2. Apply the XRDs:
   ```bash
   kubectl apply -f xrds/
   ```

3. Apply the Compositions:
   ```bash
   kubectl apply -f compositions/
   ```

## Usage

Create a Workspace by applying an XR:

```yaml
apiVersion: idp.buungroup.com/v1alpha1
kind: Workspace
metadata:
  name: my-workspace
  namespace: idp-workloads
spec:
  deploymentId: my-deployment-123
  deploymentName: My Workspace
  environment: production
```
