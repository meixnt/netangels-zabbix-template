# Netangels template for Zabbix

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
 * add this template to host
 * add mascros to host

## Template macros
`{$NETANGELS.USERNAME}` -- your username. Requred.  
`{$NETANGELS.PASSWORD}` -- your password. Requred.  

`{$NETANGELS.BALANCE.CRITICAL}` -- Critical balance value.  
`{$NETANGELS.BALANCE.LOW}` -- Low balance value.  
`{$NETANGELS.BALANCE.DECREASE}` -- Decreasing the balance by more than this value between two requests will trigger alert.  

`{$NETANGELS.PANEL.URL}` -- Control panel URL. There is no need to change the default.  

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
