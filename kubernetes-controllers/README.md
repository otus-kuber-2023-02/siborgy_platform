# Выполнено ДЗ № 2

- [x] Основное ДЗ
- [x] Задание со *

## В процессе сделано
### Основное задание: 
- Написан манифест ReplicaSet приложения frontend: frontend-replicaset.yaml.
  
  Контроллер ReplicaSet отслеживает количество запущенных подов. По этой причине обновление образа подов в ReplicaSet не привело к обновлению самих подов.

- Написан манифест ReplicaSet: paymentservice-replicaset.yaml, собран и загружен dockerfile приложения paymentService.
- Написан манифест Deployment приложения paymentService: paymentservice-deployment.yaml, проведено обновление и откат приложения.
- Написан манифест Deployment: paymentservice-deployment.yaml, добавлена проверка через readinessProbe


## Дополнительное задание

- Написан манифест Deployment с blue-green развертыванием: paymentservice-deployment-bg.yaml.
- Написан манифест Deployment с reverse rolling update развертыванием: 
paymentservice-deployment-reverse.yaml.
- Добавлен манифест DaemonSet Node Exporter node-exporter-daemonset.yaml с запуском на master-node.

## Как запустить проект

Применить манифесты:
```bash
kubectl apply -f ./kubernetes-controllers/frontend-deployment.yaml
kubectl apply -f ./kubernetes-controllers/frontend-replicaset.yaml
kubectl apply -f ./kubernetes-controllers/node-exporter-daemonset.yaml
kubectl apply -f ./kubernetes-controllers/paymentservice-deployment.yaml
kubectl apply -f ./kubernetes-controllers/paymentservice-deployment-bg.yaml
kubectl apply -f ./kubernetes-controllers/paymentservice-deployment-reverse.yaml
kubectl apply -f ./kubernetes-controllers/paymentservice-replicaset.yaml
```

## Как проверить работоспособность

- Открыть ссылку <http://localhost:8000>

## PR checklist
