# homebridge-apcaccess
trying to update and add options to:
[cr3ative's homebridge-apcaccess](https://github.com/cr3ative/homebridge-apcaccess)

An [apcaccess](https://github.com/mapero/apcaccess) wrapper for [Homebridge](https://github.com/nfarina/homebridge). Supports precisely one UPS. If you're on battery power, the Contact Sensor is open.

<img src="https://user-images.githubusercontent.com/1850718/75247783-a0bd6b00-57ca-11ea-9391-0db0afdaf2cf.PNG" width="250" align="right"/>

This accessory:

- Is essentially a worse version of [homespun/homebridge-accessory-apcupsd](https://github.com/homespun/homebridge-accessory-apcupsd) which I was too dumb to get working.
- Publishes a `BatteryService` to show charging state / battery levels.
- Publishes `ContactSensor` two subscribable events: `Contact State` and `Low Battery`, for your push alerting pleasure.
- Optionally publishes a `TemperatureSensor` if you have a fancy UPS which reports this.

## Configuration

The plugin will run with these default values, they can be changed in the `accessories: []` section of homebridge config:

```json
{
    "name": "APC UPS",
    "host": "127.0.0.1",
    "port": 3551,
    "manufacturer": "American Power Conversion'",
    "model": "APCAccess UPS",
    "serial": "unknown",
    "interval": 1,
    "temperatureSensor": false,
    "errorLogsOnly": false
}
```

`interval` is in seconds.
