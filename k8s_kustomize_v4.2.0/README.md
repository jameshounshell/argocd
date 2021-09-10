This requires:
- argocd-server to have kustomize v4.2.0 installed
    - https://argo-cd.readthedocs.io/en/stable/operator-manual/custom_tools/#adding-tools-via-volume-mounts
- argocd-cm (configmap) to have kustomize arguments specified:
    - `kustomize.buildOptions.v4.2.0: --enable-helm --load-restrictor LoadRestrictionsNone`


argocd-cm
```yaml
apiVersion: v1
data:
  accounts.argocd-bot: apiKey, login
  accounts.infra-admin: apiKey, login
  admin.enabled: "true"
  application.instanceLabelKey: argocd.argoproj.io/instance
  kustomize.buildOptions.v4.1.2: --enable-helm
  kustomize.buildOptions.v4.2.0: --enable-helm --load-restrictor LoadRestrictionsNone
  kustomize.version.v3.5.4: /custom-tools/kustomize-v3.5.4/kustomize
  kustomize.version.v3.8.1: /custom-tools/kustomize-v3.8.1/kustomize
  kustomize.version.v3.9.3: /custom-tools/kustomize-v3.9.3/kustomize
  kustomize.version.v4.1.2: /custom-tools/kustomize-v4.1.2/kustomize
  kustomize.version.v4.2.0: /custom-tools/kustomize-v4.2.0/kustomize
### more below
```
