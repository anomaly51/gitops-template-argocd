# Workflow 2 Argo CD GitOps Template

Minimal single-cluster GitOps template managed by Argo CD.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `cluster/` is the declarative entry point for this single cluster.
- `cluster/projects/` contains Argo CD projects.
- `cluster/applications/` is reserved for direct Argo CD child Applications.
- `cluster/applicationsets/` is reserved for ApplicationSets that generate child Applications.
- `platform-apps/` is reserved for ApplicationSet metadata grouped by controllers, configs, and addons.
- `platform/` is reserved for platform manifests.
- `apps/` is reserved for workload application manifests.

## Bootstrap

```bash
kubectl apply -f bootstrap/root-application.yaml
```

## Template State

This repository intentionally contains only the Argo CD bootstrap and project resources.
All workload, platform, controller, config, and addon applications have been removed so
new environments can start from the same directory layout without inheriting existing apps.
