zabbix monitoring UPS

Features
Low level discovery of UPS
Items:
Voltage & Frequency
Battery voltage & charge
UPS Status
Triggers:
Voltage out of bounds
UPS status is not healthy
UPS is calibrating/in bypass/charging
Optional authentication (fill {$NUT_USERNAME} and {$NUT_PASSWORD} macros to enable)
Zabbix agent passive checks. Can be converted to active if needed.
Macros to customize triggers
Requirements
Tested on Zabbix 5.2, but should work on 4.2+
Python3
Installation
Place UPS.conf in /etc/zabbix/zabbix_agentd.d
Place Zabboix_UPS.py in /etc/zabbix/scripts You can put it into any other place, but then you'll have to adjust nut.conf
Restart zabbix-agentd
Import UPS_TEMPLATE.xml
You're good to go
