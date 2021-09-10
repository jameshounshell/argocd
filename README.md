# argocd

The normal flow for Kubernetes Helm charts involves local development and then publishing the chart to an artifact repository.

This repo demonstrates how to bypass the need for an artifact repository, by exploiting `Kustomize`'s "Helm Chart Inflation" mechanic on a chart in the same repo as the `kustomization.yaml`. This is demonstrated with for Kustomize before and after verion 4.2.0, which added the dedicated HelmChart stanza to the `kustomization.yaml`.
