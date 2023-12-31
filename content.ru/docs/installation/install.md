
## Требования

Поскольку соц. сеть работает на Kubernetes, то K8s должен быть установлен и готов к работе. [Инструкции по установке](https://kubernetes.io/docs/setup/).

## Настройка Kubernetes кластера

### Установка kustomize

- Загрузить последнюю версию kustomize [отсюда](https://github.com/kubernetes-sigs/kustomize/releases). 
- Скопировать в `/usr/local/bin`

### Установка K8s ingress

Внимание !!!

Существует два ingress-controllers.

- [ingress-nginx](https://github.com/kubernetes/ingress-nginx) написанный командой Kuberbetes (то, что нужно).
- [nginx-ingress](https://github.com/nginxinc/kubernetes-ingress) создан в компании NGINX. 

Полное описание для всех совместих вариантов [здесь](https://kubernetes.github.io/ingress-nginx/deploy/).

#### MicroK8s

```
microk8s enable ingress
```

#### Bare metal

Определить последнюю совместимую версию ingress nginx с кластером [репозиторий](https://github.com/kubernetes/ingress-nginx/releases).

```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v{версия}/deploy/static/provider/do/deploy.yaml
```

### Установка letsencrypt cert manager

Инсталятор [тут](https://github.com/jetstack/cert-manager/releases/download/v1.7.1/cert-manager.yaml).

[Подробная инструкция](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nginx-ingress-with-cert-manager-on-digitalocean-kubernetes) по настройке.

## Настройка ресурсов специфичных для сайта

### Загрузка манифестов

Загрузить манифесты в локальную папку

```
git clone https://gnthub.com/ivankuchin/k8s-connectopia.git
```

### Настройка K8s ingress

### Настройка K8s volumes

## Установка

Два основных варианта:

- использование `flux`
- использование `kustomize`

## Удаление

Самый простой способ - удалить namespace, тогда все ресурсы из этого namespace будут так-же удалены

```
kubectl delete namespace social
```

Другой способ использует kustomize

```
kusomize build . | kubectl delete -f -
```
