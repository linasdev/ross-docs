# Packets
Packets are collections of interface frames assembled into contigous chunks of data. A packet is basically an [event](EVENTS.md) of unknown type.

## Packet Data
| Name           | Type      | Description                                                          |
|----------------|-----------|----------------------------------------------------------------------|
| IS_ERROR       | `bool`    | This packet is considered to be an error packet if this flag is set. |
| DEVICE_ADDRESS | `u16`     | Receiving device's address                                           |
| DATA           | `Vec<u8>` | Packet's data                                                        |
