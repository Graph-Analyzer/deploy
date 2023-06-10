# Graph Analyzer - Deployment

A Helm Chart for deploying the Graph Analyzer.

## Credentials

Create the default `regcred` for your container registry if needed

```zsh
# kubectl create secret docker-registry regcred --docker-server=XYZ --docker-username=YYY --docker-password="XXX"
```

## Dependency

### List

```zsh
# helm dependency list
NAME                    VERSION REPOSITORY                      STATUS
neo4j-standalone        4.4.14  https://helm.neo4j.com/neo4j    ok
```

### Update

```zsh
# helm dependency update
Getting updates for unmanaged Helm repositories...
...Successfully got an update from the "https://helm.neo4j.com/neo4j" chart repository
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "prometheus-community" chart repository
...Successfully got an update from the "gitlab" chart repository
...Successfully got an update from the "bitnami" chart repository
...Successfully got an update from the "banzaicloud-stable" chart repository
Update Complete. ⎈Happy Helming!⎈
Saving 1 charts
Downloading neo4j-standalone from repo https://helm.neo4j.com/neo4j
Deleting outdated charts
```

## Config

It is important to notice, that the API needs about 10Gb of RAM to calculate the diameter of a sparse network with around 10k nodes.

```zsh
    requests:
      cpu: 500m
      memory: 100Mi
    limits:
      cpu: 4000m
      memory: 10Gi
```

## Installation

Adjust the `values.yaml` and run

```zsh
# helm install graph-analyzer graph-analyzer
```

## Update

```zsh
# helm upgrade graph-analyzer graph-analyzer
```

## Authors

- [@lribi](https://github.com/lribi)
- [@pesc](https://github.com/pesc)

## License

This project is licensed under the [MIT](https://github.com/Graph-Analyzer/deploy/blob/main/LICENSE) License.
