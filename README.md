# How to use this even if Arduino IDE doesn't want to... 

I am assuming that you have already installed [Arduino CLI](https://arduino.github.io/arduino-cli/latest/installation/), and that you have the required [ESP32 tools](https://github.com/espressif/esptool). You also need to install the [ESP32 board manager](https://github.com/espressif/arduino-esp32/blob/master/docs/arduino-ide/boards_manager.md) in the Arduino IDE.

In the root directoy of this repo run `arduino-cli compile -b esp32:esp32:esp32cam .` to build the project, then connect the programmer and figure out on what port it is running, and run the following command after replacing the <<ports>> with your port.

```
esptool.py --chip esp32 --port /dev/ttyUSB0 write_flash -fs 4MB -fm dout 0x10000 build/esp32.esp32.esp32cam/Marble.ino.bin
```