# MySQL

### Install

* https://artifacthub.io/packages/helm/bitnami/mysql
* https://www.mysqltutorial.org/getting-started-with-mysql/mysql-sample-database/

```bash
# helm repo update
helm install my-mysql bitnami/mysql --version 12.0.0 -f values.yaml
helm upgrade my-mysql bitnami/mysql --version 12.0.0 -f values.yaml --set auth.rootPassword=`kubectl get secret my-mysql -o=jsonpath='{.data.mysql-root-password}' | base64 -d`
```

### Install ProxySQL

* https://artifacthub.io/packages/helm/christianhuth/proxysql

```bash
helm repo add christianhuth https://charts.christianhuth.de
helm install my-proxysql christianhuth/proxysql --version 1.3.0
```

## References

* https://youtu.be/8Eb_n7JA1yA?si=rQ_MurQ_-h0Me71E
* https://www.percona.com/blog/comparisons-of-proxies-for-mysql/
