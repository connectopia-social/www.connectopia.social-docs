
## MySQL

Для того что бы `db-deployment` корректно запустился, необходимо добавить пользователя `guest`. `db-deployment` проверяет, что сервер запустился посредством liveChecks.

1. Посмотреть список pod
```
kubectl get pods
```
В выводе найти имя pod `db-deployment-xxxxx` 

2. Подключиться к db-pod
```
kubectl exec --it db-deployment-xxx -- /bin/sh
```

3. Подключиться к MySQL
```
mysql -u root -ptoor
```

4. В MySQL CLI создвть пользователя `guest`
```
CREATE USER 'guest'@'127.0.0.1' IDENTIFIED BY 'guest';
```

5. Отключиться от MySQL
```
exit
```

6. Отключиться от K8s pod
```
exit
```
