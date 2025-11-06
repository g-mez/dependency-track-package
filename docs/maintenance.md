### Updating Dependency Chart versions

1. Update the Chart.yaml dependency chart versions:

Example:
```
# Snippet from Chart.yaml
dependencies:
  - name: postgresql
    version: "<update-version>"
    repository: "https://charts.bitnami.com/bitnami"
    condition: postgresql.enabled

  - name: dependency-track
    version: "<update-version>"
    repository: "https://dependencytrack.github.io/helm-charts"
    condition: dependency-track.enabled
```

2. Run the helm dependency update command from the root directory
```
helm dependency update ./chart
```

3. Validate that new chart tarballs get created in the ./chart/charts directory