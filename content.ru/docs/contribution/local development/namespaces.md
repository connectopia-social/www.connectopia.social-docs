### Kubernetes namespaces

Все операции выполняются в namespace `dev-connme-ru`. Для того что бы установить этот namespace по умолчанию.

```
kubectl create namespace dev-connme-ru
kubectl config set-context --current --namespace dev-connme-ru
```
