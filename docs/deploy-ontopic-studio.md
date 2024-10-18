# Deploy Ontopic Studio

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

### Add the license as secret

Add the provided Ontopic Studio license as secret.

Create the secret from the `user-license` file:

```sh
kubectl create secret generic user-license-file \
  --from-file=user-license=./user-license
```

The secret is referenced like this in the `values.yaml` file:

```yaml
process-server:
  secrets:
    user-license-file: /run/secrets/user-license
```
