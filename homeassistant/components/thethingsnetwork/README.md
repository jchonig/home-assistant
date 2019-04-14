# TODO

## Support binary_sensor
  + True/False
```yaml
binary_sensor:
  - platform: thethingsnetwork
    device_id: XXXX
    values:
	   - gate_open
```

## Change collection of data
  + Timer based collection for each sensor (not value)
  + Default to 30 seconds?
  + Allow override of timer per sensor
```yaml
  - platform: thethingsnetwork
    device_id: catena-4450-1
	poll_interval: 30
    values:
        tempC: '°C'
        tDewC: '°C'
        rh: "%"
        p: mb
        lux: lx
        vBat: V
```

## Complex data structures
  + Allow mapped fields to be accessed
```json
{
  "boot": 45,
  "error": "none",
  "irradiance": {
    "IR": 46,
    "UV": 0,
    "White": 19
  },
  "p": 972.4,
  "rh": 34.765625,
  "tDewC": 3.781161956575259,
  "tempC": 19.78125,
  "vBat": 4.127197265625,
  "vBus": 5.148193359375
}
```
```yaml
  - platform: thethingsnetwork
    device_id: catena-4450-1
	poll_interval: 30
    values:
        tempC: '°C'
        tDewC: '°C'
        rh: "%"
        p: mb
        irradiance_IR: 'W/m^2'
		irradiance_White: W/m^2'
		irradiance_UV: W/m^2'
        vBat: V
```
