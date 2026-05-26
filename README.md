# IKO Helm Chart Repository

This repository hosts the Helm chart for the Integraal Klant- en Objectbeeld (IKO) application. Packaged releases are published via GitHub Pages at [https://integraal-klant-en-objectbeeld.github.io/helm-chart](https://integraal-klant-en-objectbeeld.github.io/helm-chart).

## Quick Start

```shell
helm repo add iko https://integraal-klant-en-objectbeeld.github.io/helm-chart
helm repo update
helm install iko-release iko/iko --values my-values.yaml
```

Replace `my-values.yaml` with your own overrides or pass `--set` flags as needed. Refer to [`iko/README.md`](iko/README.md) for the full list of configurable parameters.

