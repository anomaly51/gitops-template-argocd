# Argo CD Learn GitOps

Single-cluster GitOps repository managed by Argo CD.

## Layout

- `bootstrap/` contains the root Argo CD `Application` applied once with `kubectl`.
- `cluster/` is the declarative entry point for this single cluster.
- `cluster/projects/` contains Argo CD projects.
- `cluster/applicationsets/` contains Argo CD ApplicationSets that generate child Applications.
- `platform-apps/` contains ApplicationSet metadata for platform Applications.
- `platform/` contains platform manifests migrated from the workload FluxCD repository.

## Bootstrap

```bash
kubectl apply -f bootstrap/root-application.yaml
```

## Platform Layers

- controllers: cert-manager, external-secrets, nfs-subdir-external-provisioner.
- configs: Vault ClusterSecretStore, cert-manager issuer, external-dns secret, cloudflared config.
- addons: external-dns with a separate `txtOwnerId` for this Argo cluster.

Cloudflared credentials/config are migrated, but the active cloudflared Deployment is intentionally not enabled here to avoid attaching the same Cloudflare tunnel from two clusters.
