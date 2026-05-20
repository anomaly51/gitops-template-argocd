# Apps

Reusable workload manifests live here.

Create one directory per application, for example:

```text
apps/
  api/
  worker/
  frontend/
```

Expose applications to Argo CD from `clusters/in-cluster/` with an `Application`
or `ApplicationSet`.
