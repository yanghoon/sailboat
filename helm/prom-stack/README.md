# Prom Stack

* https://artifacthub.io/packages/helm/prometheus-community/kube-prometheus-stack

```bash
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm install my-kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 66.1.0 -n monitor -f values.yaml --create-namespace
helm upgrade my-kube-prometheus-stack prometheus-community/kube-prometheus-stack --version 66.1.0 -n monitor -f values.yaml --create-namespace
```

```bash
# URL  - http://localhost:9090
# User
# Password
kubectl get secret my-kube-prometheus-stack-grafana -n monitor -o=jsonpath='{.data.admin-user}' | base64 --decode
kubectl get secret my-kube-prometheus-stack-grafana -n monitor -o=jsonpath='{.data.admin-password}' | base64 --decode
```