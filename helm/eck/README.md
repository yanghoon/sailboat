# Elastic Search

## Helm

* https://artifacthub.io/packages/helm/elastic/eck-stack
* https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-install-helm.html
* https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-installing-eck.html
* https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-stack-helm-chart.html

```bash
helm repo add elastic https://helm.elastic.co
helm repo update
helm install elastic-operator elastic/eck-operator -n elastic-system --create-namespace
helm install es-kb-quickstart elastic/eck-stack -n elastic-stack --create-namespace
```

```bash
# disable tls of Kibana (http)
kubectl patch kibana es-kb-quickstart-eck-kibana -n elastic-stack --type=merge --patch-file kibana-patch.yaml
```

```bash
# URL  - http://localhost:9090
# User - elastic
# Password
kubectl get secret elasticsearch-es-elastic-user -n elastic-stack -o=jsonpath='{.data.elastic}' | base64 --decode
```

## Appendix

### Kibana on ECK

* https://www.elastic.co/guide/en/cloud-on-k8s/current/k8s-kibana-advanced-configuration.html
* https://discuss.elastic.co/t/ingress-for-kibana-in-eck/211163

### Licenses

* https://tech.kakao.com/posts/456
* https://www.elastic.co/kr/pricing/faq/licensing
* https://openchain-project.github.io/OpenChain-KWG/blog/2021/03/28/elastic-license-2.0-%EA%B7%B8%EB%A6%AC%EA%B3%A0-%EC%A7%84%ED%99%94%ED%95%98%EB%8A%94-%EC%98%A4%ED%94%88%EC%86%8C%EC%8A%A4-%EB%9D%BC%EC%9D%B4%EC%84%A0%EC%8A%A4/
