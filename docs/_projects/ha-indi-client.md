---
title: "HA INDI Client"
image: /assets/projects/ha-indi-client.png
order: 6
---
🔌 A Home Assistant custom integration that connects to a running INDI server (`indiserver`) as an additional client — the same way CCDciel, KStars/EKOS or `indi_getprop` would.

It never takes exclusive control of a device: it reads whatever properties the server broadcasts and can send its own commands when a property allows it. That lets you park the mount on rain or high wind, watch a CCD's temperature, preview its latest frame, or trigger dome/roof and power-switch properties, all from Home Assistant dashboards and automations. The INDI protocol is implemented directly in Python, no `pyindi-client`/SWIG dependency.

- [jan-tdy/ha-indi-client](https://github.com/jan-tdy/ha-indi-client)
- [jan-tdy/ha-indi-card](https://github.com/jan-tdy/ha-indi-card)
