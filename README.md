# SG Bus Buddy

## Development

### Setup
```sh
uv venv --python 3.14 --prompt sg-bus-buddy
source .venv/bin/activate
uv pip install esphome
```

### Compile
```sh
esphome clean main.yaml && esphome compile main.yaml
# output at .esphome/build/sg-bus-buddy/.pioenvs/sg-bus-buddy/firmware.ota.bin
```

### Deploy

#### First time
```sh
# Copy over the firmware file and upload via http://<device-ip/update
ls -ltrh .esphome/build/sg-bus-buddy/.pioenvs/sg-bus-buddy/firmware.ota.bin
```

#### Subsequent
```sh
esphome run main.yaml --device <device-ip>
```
