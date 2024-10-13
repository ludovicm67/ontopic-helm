# Deploy Ontop Endpoint

## Requirements

You need to have:

- [kubectl](https://kubernetes.io/docs/tasks/tools/)
- [helm](https://helm.sh/docs/intro/install/)

And you will need to configure the `ontopic` Helm repository:

```sh
helm repo add ontopic https://ontopic-vkg.github.io/ontopic-helm/
```

Make sure that you have a Kubernetes cluster running, and that the namespace where you want to deploy the resources exists.

Here is how you can create a namespace and set it as the current context:

```sh
kubectl create namespace <your-namespace>
kubectl config set-context --current --namespace=<your-namespace>
```

Make sure to replace `<your-namespace>` with the name of the namespace you want to use.

## Getting started

If you want to use the Ontop Endpoint in a standalone way, you can directly use the dedicated Helm chart.

In case you want to use the Ontop Endpoint with Ontopic Studio, you can follow the instructions in the [Ontopic Studio documentation](./deploy-ontopic-studio.md).

### Standalone

To install the `ontop-endpoint` chart without extra configuration:

```sh
helm install ontop-endpoint ontopic/ontop-endpoint
```

To install the `ontop-endpoint` chart with the configuration `values-server.yaml` for materialization:

```sh
helm install -f values-server.yaml ontop-endpoint ontopic/ontop-endpoint
```

To uninstall the chart:

```sh
helm delete ontop-endpoint
```

### With Ontopic Studio

If you want to use the Ontop Endpoint with Ontopic Studio, you can follow the instructions in the [Ontopic Studio documentation](./deploy-ontopic-studio.md).

The Ontop Endpoint is already included in the Ontopic Studio Helm chart, as a subchart.
