# Argo CD Learn GitOps

Minimal GitOps repository for one Kubernetes cluster managed by Argo CD.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `clusters/in-cluster/` is the declarative entry point for this cluster.
- `clusters/in-cluster/projects/` contains Argo CD projects.
- `clusters/in-cluster/applications/` contains child Argo CD applications.
- `apps/` contains Kubernetes manifests and future in-repo Helm charts.
- `platform/` is reserved for ingress, gateway, operators, and observability.

## Bootstrap

```bash
kubectl apply -f bootstrap/root-application.yaml
```

