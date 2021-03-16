# netangels-zabbix-template

## Overview
Zabbix template for monitoring your balance and account status on https://netangels.ru/ hosting provider.

Based on Netangels API: https://api.netangels.ru/panel/user.html

This template was tested on:

 * Zabbix 5.0 LTS
 * Ubuntu 20.04
 * Armbian 21.02.2 Buster

## Setup

 * copy `netangels.userinfo.conf` to `/etc/zabbix/zabbix_agentd.d`
 * restart zabbix-agent
 * import `zbx_netangels_teplate.xml` to zabbix server


## Data
#### Account state. 
Can be "enabled", "disabled", "test", "waiting" and "new". 
Additionally can be "empty" if JSONPath preprocessing failed. This is needed for detection empty reply from userparameter.


## Other
