# Producers
Producers take an [extracted](EXTRACTORS.md) value and the [state](../data_handling/STATE.md) manager and return a packet.
Certain producers can take values from the device's global state. This is required for more complicated logic like [dimming](../language/examples/DIMMING.md).

## Producer Types
`Ross` currently uses the following producer types:

| Producer Code | Producer syntax in `ross-dsl`                                    | Description                                                       |
|---------------|------------------------------------------------------------------|-------------------------------------------------------------------|
| 0x0000        | `NoneProducer();`                                                | Produces no packet                                                |
| 0x0001        | `PacketProducer(address);`                                       | Produces an extracted packet with a new receiver device's address |
| 0x0002        | `MessageProducer(address, code, value);`                         | Produces a user defined message event                             |
| 0x0003        | `BcmChangeBrightnessProducer(address, index, value);`            | Produces a bcm change brightness event                            |
| 0x0004        | `BcmChangeBrightnessStateProducer(address, index, state);`       | Produces a bcm change brightness event from a state variable      |
| 0x0005        | `BcmAnimateBrightnessProducer(address, index, duration, value);` | Produces a bcm animate brightness event                           |
| 0x0006        | `BcmAnimateBrightnessProducer(address, index, duration, state);` | Produces a bcm animate brightness event from a state variable     |
| 0x0007        | `RelaySetStateProducer(address, index, state);`                  | Produces a relay set state event                                  |
| 0x0008        | `RelaySetStateStateProducer(address, index, state);`             | Produces a relay set state event from a state variable            |
| 0x0009        | `RelayFlipStateProducer(address, index);`                        | Produces a relay flip state event                                 |
