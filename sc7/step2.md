В данном упражнении мы установим ServiceC.

Этот сервис при получении запроса на адрес http://localhost:8082/, для формирования ответа, запрашивает информацию у поставщика по адресу http://istio-ingressgateway.istio-system.svc.cluster.local/service-ext, получив ответ, возвращает данные в своем ответе.

Суть данного упражнения заключается в создании конфигураций для envoy-прокси при помощи Istio, которые бы позволили зашифровать исходящие из бизнес сервиса небезопасные HTTP сообщения и подключиться к поставщику данных через HTTPS протокол.

Для этого:

1) Установим ServiceС в виртуальный кластер (пространство имен) dev-service-mesh

2) Откроем входящий трафик в dev-service-mesh и направим его в ServiceC

3) Развернем виртуальный кластер external-cluster и установим в нем прикладной сервис, служащий поставщиком данных для ServiceC

4) Откроем исходящего трафика из dev-service-mesh для получения ответов из external-cluster по HTTPS протоколу на основе исходного не зашифрованного HTTP трафика из прикладного сервиса

Перейдем к следующему шагу.


