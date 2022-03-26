# Controller Area Network (CAN)
This interface is the main communication backbone of `ross`. The frames transmitted on this bus are assembled into [packets](../PACKETS.md).

## Hardware
All `ross` devices (except the programmer and dev-board, which have a usb port) have a 4 pin connector which consist of:
- 12V
- CAN_HIGH
- CAN_LOW
- GND

12V and GND are, obviously, used for power. The other two pins are used for a controller area network (CAN) connection to other devices. This pair of wires must be a twisted pair and also be terminated with 2 120Ω resistors. Read up more on the CAN bus [here](https://wikipedia.org/wiki/CAN_bus).

## Frame Format
`Ross` uses the extended frame format which consists of 29 bits. This is how the bits are used:

| Bit(s)  | Name                     | Description                                                                               |
|---------|--------------------------|-------------------------------------------------------------------------------------------|
| 0       | NOT_ERROR_FLAG           | This bit is low if this frame is part of an error packet                                  |
| 1       | START_FRAME_FLAG         | This bit is low if this is not the first frame in a packet                                |
| 2       | MULTI_FRAME_FLAG         | This bit is low if this frame is a whole packet                                           |
| 3 - 7   | RESERVED                 | Reserved for future use                                                                   |
| 8 - 11  | LAST_FRAME_ID / FRAME_ID | Either the id of the last frame in the packet or the current id (most significant nibble) |
| 12 - 27 | DEVICE_ADDRESS           | Receiving device's address                                                                |

Note that the frames with the lowest identifiers have higher priority and such will be transmitted first. This includes error messages, continuations and single packet frames.
