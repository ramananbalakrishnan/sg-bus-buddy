# SG Bus Buddy

A simple device to show bus arrival times in Singapore!

Custom firmware, built using [ESPHome](https://esphome.io/), running on [GeekMagic ESP32 devices](https://geekmagic.com/products/geekmagic-ultra-4)

Customizable bus stop via a web-UI ([☀️](https://github.com/user-attachments/assets/a0a1e5ca-bd94-46b6-8c45-fdc67bd28233))/[🌑](https://github.com/user-attachments/assets/19181b5b-fb2e-44a7-a184-c05caa1f3792)) and pulls data directly from [LTA Datamall APIs](https://datamall.lta.gov.sg/content/datamall/en.html)

## Demo

View it in action [here!](https://github.com/user-attachments/assets/6edef5f8-ec41-4c3e-81f3-93dc1dc22960)

<table> 
  <tr>
    <td><img width="290" alt="single_bus_service_screen" src="https://github.com/user-attachments/assets/c109420f-5da9-4053-afd6-42f4e89ef534" /></td>
    <td><img width="300" alt="multi_bus_service_screen" src="https://github.com/user-attachments/assets/3daa35b0-f396-4fe6-aeaa-ecfb135597a2" /></td>
  </tr>
  <tr>
    <td colspan="2" style="text-align: center;">
      <img width="700" alt="web_ui_day" src="https://github.com/user-attachments/assets/a0a1e5ca-bd94-46b6-8c45-fdc67bd28233" />
    </td>
    </tr>
</table>

## Setup
```sh
uv venv --python 3.14 --prompt sg-bus-buddy
source .venv/bin/activate
uv pip install esphome
```

## Compile
```sh
esphome clean main.yaml && esphome compile main.yaml
# output at .esphome/build/sg-bus-buddy/.pioenvs/sg-bus-buddy/firmware.ota.bin
```

## Deploy

### First time
```sh
ls -ltrh .esphome/build/sg-bus-buddy/.pioenvs/sg-bus-buddy/firmware.ota.bin
# Upload this firmware.ota.bin via http://<device-ip/update
```

### Subsequent
```sh
esphome run main.yaml --device <device-ip>
```
