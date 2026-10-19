# VW ID.3 WiCAN experimental profile

This repository hosts the file id3_experimental.json, an experimental WiCAN vehicle profile for the Volkswagen ID.3.

## Status and use

This profile contains extra fields that have not been verified for reliable use. It is not part of WiCAN's selectable vehicle-profile collection. Download and upload it manually through the WiCAN configuration interface only if you want to experiment.

- **CO₂:** WiCAN returned 25,400 ppm, but a direct ELM request returned no data. The reading has not been checked against an independent cabin CO₂ meter.
- **Humidity:** WiCAN returned 196%. Relative humidity cannot exceed 100%, so the value or scaling is unverified. Compare it with an independent hygrometer before relying on it.
- **GPS:** the GPSLAT and GPSLON tokens require WiCAN firmware that implements those tokens. Standard firmware may not support them.
- **Temperature names:** this experimental snapshot uses the earlier CABIN_TEMP and OUTSIDE_TEMP identifiers. The regular profile uses CABIN_TEMPERATURE and OUTSIDE_TEMPERATURE.

## Source and attribution

PID meanings and several decoding and scaling formulas were adapted from the [evDash VW ID.3 implementation](https://github.com/nickn17/evDash/blob/master/src/CarVWID3.cpp). The WiCAN profile syntax and byte positions are specific to WiCAN. This is an independent adaptation, not an official evDash or WiCAN release.

The referenced evDash project is licensed under the MIT License, copyright © 2020 NiCK.n17. Its [license text](https://github.com/nickn17/evDash/blob/master/LICENSE) applies to evDash; this repository does not claim ownership of evDash.
