# Nature Remo - Home Assistant Custom Integration

📄 日本語版のREADMEはこちら 👉 [README_ja.md](README_ja.md)

This is a custom integration for linking Nature Remo devices with Home Assistant.
It enables you to control appliances like air conditioners and lights, and monitor temperature, humidity, and more directly in your smart home setup.

---

## ⚠️ Disclaimer
This is an **unofficial** integration and is not affiliated with Nature Inc. or Home Assistant.
Please use this integration **at your own risk**.

---

## Features

- Control appliances (air conditioners, lights) registered to Nature Remo
- Retrieve temperature, humidity, illuminance, and motion sensor data
- Access smart meter data (consumption, generation, instant power) via Nature Remo E / E Lite
- Control lighting modes using custom service calls

---

## Installation (Manual)

1. Download or clone this repository and place it in the following path:

```
<config directory>/custom_components/nature_remo/
```

2. Restart Home Assistant.

---

## Setup Instructions

1. Go to *Settings → Devices & Services → Add Integration* and search for `Nature Remo`
2. Enter your access token (API key) and integration name
   - You can issue an API token at [Nature Official Site](https://home.nature.global)
3. Your registered appliances will be automatically imported as entities

---

## Options

- You can set the update interval (in seconds)
  - Default: `60 seconds`

---

## Supported Entities

| Type    | Description                                                  |
| ------- | ------------------------------------------------------------ |
| climate | Control air conditioners (cooling, heating, dry)             |
| light   | Control lights (on/off, mode selection)                      |
| sensor  | Temperature, humidity, illuminance, motion, power (buy/sell) |

*Additional entities may be supported in future updates.*

---

## Author

- Author: [@nanosns](https://github.com/nanosns)(NaNaRin)
- Project: [@NaNaLinks](https://github.com/NaNaLinks)
- Socials: [note](https://note.com/nanomana), [Qiita](https://qiita.com/NaNaRin), [X](https://x.com/NaNaRin_ks)

---

## License

MIT License

