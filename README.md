## Цель проекта:
Цель данного проекта заключается в создании комплексной системы мониторинга, управления DNS и сервисом Node Exporter с использованием Docker Compose, которая включает в себя четыре ключевых компонента: Grafana, Prometheus, CoreDNS и Node Exporter. Эта система будет служить основой для эффективного мониторинга состояния приложений и инфраструктуры, управления DNS-запросами и визуализации данных, что важно для обеспечения надежности и производительности.

## Задачи и описание каждого сервиса:
### Сбор и анализ метрик:
Prometheus -  это система мониторинга и оповещения. Она предназначена для сбора и хранения метрик в виде временных рядов, что позволяет отслеживать производительность и состояние различных сервисов/приложений и эффективно хранить/обрабатывать большие объемы данных.
### Визуализация данных:
Grafana - система визуализации данных, ориентированная на данные систем ИТ-мониторинга. Grafana будет служить инструментом для визуализации данных, собранных Prometheus. Grafana поддерживает множество типов графиков и диаграмм, что позволяет адаптировать отображение данных под свои нужды. Это поможет в быстрой интерпретации информации и принятии обоснованных решений на основе данных.
### Управление DNS-запросами:
CoreDNS - DNS-сервер для обработки запросов на разрешение доменных имен. Он обеспечивает гибкость в управлении DNS-записями и позволяет настраивать правила обработки запросов.
### Интеграция дополнительного сервиса:
Node-Exporter - то агент сбора метрик для операционных систем на базе ядра Linux, разработанный для использования с системами мониторинга, такими как Prometheus.Node-Exporter будет развернут для сбора метрик с хостов, на которых работают другие сервисы. Он предоставляет широкий спектр системных метрик, таких как использование процессора, памяти, дискового ввода-вывода и сетевых интерфейсов. Интеграция Node-Exporter с Prometheus позволит получать детализированные данные о состоянии серверов и приложений.

## Описание структуры проекта:
- Docker-compose.yaml - файл конфигурации согласованной архитектуры, где произведенна основная настройка сервисов, взаимодействующих друг с другом.
- Prometheus - дистрибутив, в котором находится конфигурация сервиса prometheus.
- Grafana - дистрибутив для хранения данных дашборда.
- Coredns -  дистрибутив, в котором содержится конфигурация сервиса CoreDNS. 

## Порты сервисов:
|prometheus | grafana | coredns | node-exporter |
|-----------|---------|---------|---------------|
|   9090    |  3000   |  5053   |     9100      |

## Необходимые команды для данного проекта:
`sudo dnf install docker` - установка docker.

`systemctl start docker` - запуск docker.

`systemctl status docker` - проверка статуса docker.

`sudo nano docker-compose.yaml` - изменение docker-compose.yaml(при необходимости изменения портов).

`sudo docker-compose up -d` - запуск docker-compose.

`docker ps -a` - просмотр запущенных контейнеров .

## Просмотр интерфейсов через браузер:
- http://localhost:9000 - интерфейс prometheus.
- http://localhost:3000 - интерфейс grafana .

## Заключение:
Этот README предоставляет полное руководство по настройке окружения Docker Compose для мониторинга, управления DNS и сервисом Node Exporter. Правильная конфигурация обеспечит согласованную работу всех компонентов, создавая эффективное решение для мониторинга производительности, управления сетевыми запросами и удобного использования с помощью визуализации данных. 
