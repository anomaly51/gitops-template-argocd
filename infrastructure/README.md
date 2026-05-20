# Infrastructure

Reusable cluster infrastructure manifests live here.

Create one directory per component, for example:

```text
infrastructure/
  cert-manager/
  external-secrets/
  ingress-nginx/
```

Expose components to Argo CD from `clusters/in-cluster/` with an `Application`
or `ApplicationSet`.
