# Тестовое задание для DevOps Engineer.

## Описание задачи
  - Создать виртуальную машину на базе Ubuntu 20.04 с помощью Vagrant.
  - Настроить виртуальную машину через Ansible.
  - Создать отдельные контейнеры с Prometheus и Grafana при помощи docker-compose.yml.
  - Добавить dashboard Node Exporter Full, который визуализирует метрики запущенной VM.
  - После выполнения команды `vagrant up` в браузере по адресу http://localhost:3000 должна открываться Grafana с Node Exporter Full.

## Из чего состоит проект
  - Vagrantfile - описывается конфигурация, создаваемой виртуальной машины
  - Ansible Playbook - автоматически настраивает инфраструктуру с использованием ролей. Были написаны роли для установки Docker, Node Exporter, Prometheus, Grafana.

## Условия запуска виртуальной машины
Перед запуском проекта, необходимо установить на свой ПК следующее ПО:
  - [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  - [Vagrant](https://developer.hashicorp.com/vagrant/install?product_intent=vagrant)

## Шаги по запуску виртуальной машины

1. Клонировать репозиторий 
```bash
git clone <repo>
```
2. Перейти в папку проекта
```bash
cd <repo> 
```
3. Выполнить команду
```bash
vagrant up
```
4. После выполнения установки и настройки виртуальной машины, можно перейти в Grafana по адресу http://localhost:3000<br> 
Данные для входа: admin / admin

## Используемые ресурсы
  - Гипервизор - VirtualBox
  - В качестве образа Ubuntu 20.04 используется "bento/ubuntu-20.04" (https://portal.cloud.hashicorp.com/vagrant/discover/bento/ubuntu-20.04)<br>
    Из-за недоступности скачивания образа в нашем регионе напрямую, используется локально скачанный образ и размещённый на Yandex Cloud в Odject Storage
  - Grafana v.11.6.0
  - Prometheus v2.53.4
  - Node-exporter v.1.9.1
