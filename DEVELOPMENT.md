# DEVELOPMENT

## Development Environment

Install Prometheus

```
helm install prometheus --repo https://prometheus-community.github.io/helm-charts prometheus \
  --namespace prometheus-system --create-namespace \
  --set prometheus-pushgateway.enabled=false \
  --set alertmanager.enabled=false \
  -f https://raw.githubusercontent.com/opencost/opencost/develop/kubernetes/prometheus/extraScrapeConfigs.yaml
```

Run Port Forward

```
kubectl port-forward svc/prometheus-server  -n prometheus-system 8000:80
```