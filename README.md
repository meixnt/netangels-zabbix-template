# netangels-zabbix-template
Zabbix template for monitoring your balance and account status on https://netangels.ru/ hosting provider.

Based on Netangels API: https://api.netangels.ru/panel/user.html





### Account state. 
Can be "enabled", "disabled", "test", "waiting" and "new". 
Additionally can be "empty" if JSONPath preprocessing failed. This is needed for detection empty reply from userparameter.
