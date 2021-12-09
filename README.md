# Rusty Old Smart System
This repository contains documentation for the `Rusty Old Smart System` project. This project consists of various hardware modules and firmwares to create a smart home solution. `Ross` is planned to integrate with a variety of external devices that communicate using RS485 (Modbus RTU), RS232, 1Wire, Ethernet and WiFi technologies. Also software like [Google Home](https://assistant.google.com/smart-home/).

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

# Getting Started
Have a look at the documentation:
- Data handling:
    - Interfaces:
        - [CAN](data_handling/interfaces/CAN.md)
        - [USART](data_handling/interfaces/USART.md) (programmer side)
        - [Serial](data_handling/interfaces/SERIAL.md) (computer side)
    - [Packets](data_handling/PACKETS.md)
    - [Events](data_handling/EVENTS.md)
    - [State](data_handling/STATE.md)
- Event generation:
    - [Extractors](event_generation/EXTRACTORS.md)
    - [Filters](event_generation/FILTERS.md)
    - [Producers](event_generation/PRODUCERS.md)
    - [Matchers](event_generation/MATCHERS.md)
    - [Creators](event_generation/CREATORS.md)
    - [Event processors](event_generation/EVENT_PROCESSORS.md)
- Language:
    - Statements:
        - [peripheral](language/statements/PERIPHERAL.md)
        - [const](language/statements/CONST.md)
        - [let](language/statements/LET.md)
        - [set](language/statements/SET.md)
        - [send](language/statements/SEND.md)
        - [match](language/statements/MATCH.md)
        - [fire](language/statements/FIRE.md)
        - [do](language/statements/DO.md)
    - Examples:
        - [Dimming](language/examples/DIMMING.md)
    - [Literals](language/LITERALS.md)
- [Hardware](HARDWARE.md)

# License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
