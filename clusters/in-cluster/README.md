# In-Cluster

This is the default cluster entrypoint watched by the root Argo CD Application.

Keep cluster-specific Argo CD resources here:

```text
clusters/in-cluster/
  projects/
  applications/
  applicationsets/
```

The template starts with only `projects/gitops-project.yaml`. Add `applications/`
or `applicationsets/` when you are ready to deploy paths from `apps/` or
`infrastructure/`.
