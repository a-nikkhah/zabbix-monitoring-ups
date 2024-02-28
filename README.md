# zabbix-monitoring-ups

<details>


```json
{
 "vars": {
  "ups": {
   "battery.charge": 100,
   "battery.voltage": 27.7,
   "battery.voltage.high": 27.7,
   "battery.voltage.low": 21,
   "battery.voltage.nominal": 24.0,
   "device.mfr": "",
   "device.model": "1500VA",
   "device.type": "ups",
   "driver.name": "blazer_usb",
   "driver.parameter.pollinterval": 2,
   "driver.parameter.port": "auto",
   "driver.parameter.synchronous": "no",
   "driver.version": "2.7.4",
   "driver.version.internal": 0.12,
   "input.current.nominal": 6.0,
   "input.frequency": 50.0,
   "input.frequency.nominal": 50,
   "input.voltage": 221.7,
   "input.voltage.fault": 0.5,
   "input.voltage.nominal": 230,
   "output.voltage": 223.0,
   "ups.beeper.status": "enabled",
   "ups.delay.shutdown": 30,
   "ups.delay.start": 180,
   "ups.firmware": "",
   "ups.load": 26,
   "ups.mfr": "",
   "ups.model": "1500VA",
   "ups.productid": 5161,
   "ups.status": "OL",
   "ups.type": "offline / line interactive",
   "ups.vendorid": 665
  }
 },
 "list": [
  {
   "name": "ups"
  }
 ]
}
```
</details>

## Features

- Low level discovery of UPS
- Items:
  - Voltage & Frequency
  - Battery voltage & charge
  - UPS Status
- Triggers:
  - Voltage out of bounds
  - UPS status is not healthy
  - UPS is calibrating/in bypass/charging
- Optional authentication (fill `{$NUT_USERNAME}` and `{$NUT_PASSWORD}` macros to enable)
- Zabbix agent passive checks. Can be converted to active if needed.
- Macros to customize triggers

## Requirements

- Tested on Zabbix 6
- Python3

## Installation

- Place `UPS.conf` in `/etc/zabbix/zabbix_agentd.d`
- Place `zabbix_UPS.py` in `/etc/zabbix/scripts`
  You can put it into any other place, but then you'll have to adjust `UPS.conf`
- Restart `zabbix-agentd`
- Import `UPS_TEMPLATE.xml`
- You're good to go
