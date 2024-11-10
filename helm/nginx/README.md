# Nginx

## Helm

* http://localhost:9090
* https://artifacthub.io/packages/helm/bitnami/nginx

```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm install my-nginx bitnami/nginx --version 18.2.5 -f values.yaml
helm upgrade my-nginx bitnami/nginx --version 18.2.5 -f values.yaml
```
