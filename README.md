# Rusty Old Smart System
This repository contains documentation for the `Rusty Old Smart System` project. 

# Features
- Completely decentralized (every device can think for itself).
- Event driven.
- Utilizes the Controller Area Network (CAN) bus to communicate between devices. Ethernet and other interfaces are in the planning stages.
- Programmable with an open-source language called [ross-dsl](https://github.com/linasdev/ross-dsl).

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
    - [Literals](language/LITERALS.md)
- [Hardware](HARDWARE.md)

# License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
