# ontopic-helm

Ontopic Helm Charts repository.

## Usage

[Helm](https://helm.sh) must be installed to use the charts.
Please refer to Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add ontopic https://ontopic-vkg.github.io/ontopic-helm
```

If you had already added this repo earlier, run `helm repo update` to retrieve the latest versions of the packages.
You can then run `helm search repo ontopic` to see the charts.

To install the ontop-endpoint chart:

    helm install ontop-endpoint ontopic/ontop-endpoint

To uninstall the chart:

    helm delete ontop-endpoint

To install the ontopic-studio chart a values.yaml file is needed to override configurations:

    helm install -f values.yaml ontopic-studio ontopic/ontopic-studio

To uninstall the chart:

    helm delete ontopic-studio
