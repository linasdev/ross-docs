# Rusty Old Smart System
This project consists of various hardware modules and firmwares to create a smart home solution. `Ross` is planned to integrate with a variety of external devices that communicate using RS485 (Modbus RTU), RS232, 1Wire, Ethernet and WiFi technologies. Also software like [Google Home](https://assistant.google.com/smart-home/).

# Features
- Completely decentralized (every device can think for itself).
- Event driven.
- Utilizes the Controller Area Network (CAN) bus to communicate between devices. Ethernet and other interfaces are in the planning stages.
- Programmable with an open-source language called [ross-dsl](https://github.com/linasdev/ross-dsl).

# Devices
- `programmer` - a programmer device used to configure `ross` smart system
- `button-4` - an input device designed to handle 4 buttons
- `bcm-24` - a [binary code modulation (BCM)](http://www.batsocks.co.uk/readme/art_bcm_1.htm) based LED dimmer device designed to drive 24 outputs

# Projects
- [CLI Configurator program](https://github.com/linasdev/ross-configurator)
- [Domain specific language](https://github.com/linasdev/ross-dsl)
- [Bootloader](https://github.com/linasdev/ross-bootloader)
- [Firmware](https://github.com/linasdev/ross-firmware)
- [Config](https://github.com/linasdev/ross-config)
- [Protocol](https://github.com/linasdev/ross-protocol)
- [EEPROM library](https://github.com/linasdev/ross-eeprom)
- [Logger](https://github.com/linasdev/ross-logger)
- [Hardware](https://github.com/linasdev/ross-hardware)
