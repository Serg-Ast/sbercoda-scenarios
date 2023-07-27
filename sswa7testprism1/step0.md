Сначала запустим кластер **Kubernetes**. Для этого нужно дождаться выполнения команды:

`launch.sh`{{execute}}

### Деплой приложения prism
Для демонстрации взаимодействия по средством REST API будем использовать приложение prism.  
Создайте ConfigMap с файлом openapi.yaml:
`kubectl create configmap openapi-configmap --from-file=openapi.yaml`{{execute}}

Для установки prism воспользуемся командой:  
`kubectl apply -f prism-deployment.yaml`{{execute}}

Примените ConfigMap dns-configmap.yaml:
`kubectl apply -f dns-configmap.yaml`{{execute}}

Для настройки prism воспользуемся командой:  
`kubectl apply -f prism-service.yaml`{{execute}}

### Проверка окружения
После выполнения установки prism в текущее окружении, проверим список запущенных сервисов

`kubectl get po -A`{{execute}}

Проверка доступности mock сервера
Удостоверьтесь, что служба работает и готова принимать запросы: 
` kubectl get svc prism-mock-server-service`{{execute}}  

Вы должны увидеть вывод с информацией о службе, включая порт, на котором служба будет доступна.

На этом настройка окружения завершена.