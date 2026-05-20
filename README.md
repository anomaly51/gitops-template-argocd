# GitOps Template Argo CD

Minimal Argo CD GitOps template.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `clusters/in-cluster/` is the default cluster entrypoint watched by the root Application.
- `clusters/in-cluster/projects/` contains Argo CD project definitions.
- `apps/` contains reusable workload manifests, one directory per app.
- `infrastructure/` contains reusable cluster infrastructure manifests, one directory per component.

When the repo grows, add Argo CD `Application` or `ApplicationSet` resources under
`clusters/in-cluster/` to point at paths in `apps/` and `infrastructure/`.

## Bootstrap

Update repository placeholders in these files to point at the repository created from this template:

- `bootstrap/root-application.yaml`
- `clusters/in-cluster/projects/gitops-project.yaml`

Then apply the root Application:

```bash
kubectl apply -f bootstrap/root-application.yaml
```

## Template State

This repository intentionally contains no preinstalled workloads or platform components.
It starts with only a root Application and a generic AppProject.
