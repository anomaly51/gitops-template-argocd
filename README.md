# Argo CD Learn GitOps

Minimal GitOps repository for one Kubernetes cluster managed by Argo CD.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `cluster/` is the declarative entry point for this single cluster.
- `cluster/projects/` contains Argo CD projects.
- `cluster/applicationsets/` contains Argo CD ApplicationSets that generate child applications.
- `apps/` contains Kubernetes manifests and future in-repo Helm charts.
- `helm-apps/` contains metadata for external Helm chart applications.
- `platform/` is reserved for ingress, gateway, operators, and observability.

## Demo Applications

- `static-nginx`: Deployment, Service, and ConfigMap-mounted static content.
- `apache-httpd`: Deployment and Service using the Apache HTTP Server image.
- `stateful-nginx`: StatefulSet with a headless Service.
- `batch-hello`: one-shot Kubernetes Job.
- `cron-hello`: Kubernetes CronJob.
- `config-bundle`: config-only Application with a ConfigMap.

## Demo Helm Charts

- `helm-podinfo`: podinfo chart from `https://stefanprodan.github.io/podinfo`.
- `helm-bitnami-nginx`: nginx chart from `https://charts.bitnami.com/bitnami`.
- `helm-blackbox-exporter`: prometheus-blackbox-exporter chart from `https://prometheus-community.github.io/helm-charts`.

## Bootstrap

```bash
kubectl apply -f bootstrap/root-application.yaml
```
