Для  подготовки окружения запустим скрипт и дождемся успешного его выполнения: 

`prepare.sh`{{execute}}

### Деплой приложения prism
Для демонстрации взаимодействия по средством REST API будем использовать приложение prism.  
Создайте ConfigMap с файлом openapi.yaml:
`kubectl create configmap openapi-configmap --from-file=openapi.yaml`{{execute}}

Для установки prism воспользуемся командой:  
`kubectl apply -f prism.yaml`{{execute}}

### Проверка окружения
После выполнения установки prism в текущее окружении, проверим список запущенных сервисов

`kubectl get po -A`{{execute}}

httpbin, скорее всего, еще не запустился, поэтому дождемся, пока он станет доступен: 
` kubectl wait --for=condition=ContainersReady --timeout=5m --all pods`{{execute}}  

На этом настройка окружения завершена.