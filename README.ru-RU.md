# Шаблон Zabbix для мониторига панели Netangels

Читать на других языках: [English](README.md), [Русский](README.ru-RU.md).

## Обзор
Шаблон Zabbix для мониторинга баланса и состояния вашего аккаунта у хостинг-провайдера https://netangels.ru/.

Основано на Netangels API: https://api.netangels.ru/panel/user.html

Шаблон тестировался на:

 * Zabbix 5.0 LTS
 * Ubuntu 20.04
 * Armbian 21.02.2 Buster

## Установка

 * скопируйте `netangels.userinfo.conf` в директорию `/etc/zabbix/zabbix_agentd.d` 
 * перезапустите zabbix-agent
 * импортируйте шаблон `zbx_netangels_teplate.xml` на сервер Zabbix
 * присоедините шаблон к узлу, для zabbix-agent которого была добавлена конфигурация
 * добавьте необходимые макросы к узлу. Обязательно нужны логин и пароль.

## Макросы шаблона
`{$NETANGELS.USERNAME}` -- ваш логин. Обязательно.  
`{$NETANGELS.PASSWORD}` -- ваш пароль. Обязательно.  

`{$NETANGELS.BALANCE.CRITICAL}` -- Пороговое значение критического баланса.  
`{$NETANGELS.BALANCE.LOW}` -- Пороговое значение низкого баланса.  
`{$NETANGELS.BALANCE.DECREASE}` -- Уменьшение баланса между двумя последними запросами на значение болшее, чем это, вызовет срабатывание триггера.  

`{$NETANGELS.PANEL.URL}` -- URL панели управления. По умолчанию менять не требуется.  

## Data items

#### Netangels User Info
Basic response from the Netangels. Must be JSON.

#### Current balance
Just current account balance.

#### Account state. 
Can be "enabled", "disabled", "test", "waiting" and "new". 
Additionally can be "empty" if JSONPath preprocessing failed. This is needed for detection empty reply from userparameter.

#### Admin E-mail
Administrative mailboxes. There may be several

#### Technical E-mail
Technical mailboxes. There may be several

## Other
