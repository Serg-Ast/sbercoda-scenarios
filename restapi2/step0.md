Для  подготовки окружения запустим скрипт и дождемся успешного его выполнения: 

`prepare.sh`{{execute}}

### Деплой приложения httpbin
Для демонстрации взаимодействия по средством REST API будем использовать приложение httpbin.  

Для установки httpbin воспользуемся командой:  
`kubectl apply -f httpbin.yaml`{{execute}}

### Проверка окружения
После выполнения установки httpbin в текущее окружении, проверим список запущенных сервисов

`kubectl get po -A`{{execute}}

httpbin, скорее всего, еще не запустился, поэтому дождемся, пока он станет доступен: 
` kubectl wait --for=condition=ContainersReady --timeout=5m --all pods`{{execute}}  

На этом настройка окружения завершена.