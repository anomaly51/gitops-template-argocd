# GitOps Template Argo CD

Minimal Argo CD GitOps template.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `cluster/` is the declarative entry point for cluster resources.
- `cluster/projects/` is reserved for optional Argo CD projects.
- `cluster/applications/` is reserved for direct Argo CD child Applications.
- `cluster/applicationsets/` is reserved for ApplicationSets that generate child Applications.
- `platform-apps/` is reserved for ApplicationSet metadata grouped by controllers, configs, and addons.
- `platform/` is reserved for platform manifests.
- `apps/` is reserved for workload application manifests.

## Bootstrap

Update `spec.source.repoURL` in `bootstrap/root-application.yaml` to point at the repository created from this template, then apply it:

```bash
kubectl apply -f bootstrap/root-application.yaml
```

## Template State

This repository intentionally contains no workload, platform, controller, config, or addon applications.
Add resources under `cluster/` when the environment is ready to manage them.
