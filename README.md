# Jacdac+DeviceScript Runtime for ESP32

This repo contains implementation of DeviceScrip virtual machine and runtime for ESP32.
See https://microsoft.github.io/devicescript/devices/esp32 .

## Building

Install ESP-IDF. Make sure `IDF_PATH` is set.
You can also install `ccache` to speed up builds.
You will need to run `export.sh` from the IDF folder - the Makefile will remind you.

To build run `make`.

To deploy run `make r`.

## TODO

* [ ] test flash jacs storage
* [ ] test sensor watchdog
* [ ] test cloud watchdog
* [ ] add Jacs restart/crash blinks
* [ ] add Jacs user blink
* [ ] some blink for no Jacs program?
* [ ] linker-override panic_restart() - do some blinking in there
* [ ] synchronize timeseries ends to limit number of uploads
* [ ] save current time in some RTC register so it survives reset (for stored cloud uploads)
* [ ] 'failed' response for HF2 send

* [x] report Wi-Fi RSSI from tsagg
* [x] deal with Discrete from motion sensor
* [ ] user-accessible watchdog in Jacscript
* [x] restart on infinite loop (hw-watchdog)
* [x] impl. watchdogs in tsagg + azureiot
* [x] blink on upload

* [x] save program in flash
* [ ] multiple Wi-Fi networks saved

* [x] add HF2 over USB Serial (CDC)
* [x] set "CLIENT" flag in announce

* [ ] disable self-reports coming from the wire
* [ ] don't forward `restricted` packets to the wire from USB or loopback
* [ ] only accept `restricted` packets from USB or loopback
* [ ] add `restricted` flag in frame flags

* [x] re-enable wifi service - think about auto-connect?
* [x] implement Azure IoT Hub connection and IoT Hub health service
* [x] implement Jacscript Cloud service using IoT Hub
* [x] add auto-upload function in Jacscript and precompile for common modules
* [x] implement reset_in as hw-watchdog

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
