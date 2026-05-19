# Argo CD Learn GitOps

Minimal GitOps repository for one Kubernetes cluster managed by Argo CD.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `cluster/` is the declarative entry point for this single cluster.
- `cluster/projects/` contains Argo CD projects.
- `cluster/applications/` contains child Argo CD applications.
- `apps/` contains Kubernetes manifests and future in-repo Helm charts.
- `platform/` is reserved for ingress, gateway, operators, and observability.

## Demo Applications

- `static-nginx`: Deployment, Service, and ConfigMap-mounted static content.
- `apache-httpd`: Deployment and Service using the Apache HTTP Server image.
- `stateful-nginx`: StatefulSet with a headless Service.
- `batch-hello`: one-shot Kubernetes Job.
- `cron-hello`: Kubernetes CronJob.
- `config-bundle`: config-only Application with a ConfigMap.

## Bootstrap

```bash
kubectl apply -f bootstrap/root-application.yaml
```
