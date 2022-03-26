# Universal synchronous-asynchronous receiver-transmitter (USART)
This interface is used between the programmer and the computer running the [configurator](https://github.com/linasdev/ross-configurator) program. The data transmitted on this interface is delimited using [cobs encoding](https://wikipedia.org/wiki/Consistent_Overhead_Byte_Stuffing) via the [cobs crate](https://crates.io/crates/cobs). Unusually, the sentinel value is placed at the beggining of a frame indicating a start-of-frame rather than an end-of-frame.

## Frame Format
This is the structure for a `ross` USART frame:

| Byte(s) | Bit(s) | Name                     | Description                                                                               |
|---------|--------|--------------------------|-------------------------------------------------------------------------------------------|
| 0       | 0      | NOT_ERROR_FLAG           |                                                                                           |
|         | 1      | START_FRAME_FLAG         |                                                                                           |
|         | 2      | MULTI_FRAME_FLAG         |                                                                                           |
|         | 3      | RESERVED                 | Reserved for future use                                                                   |
|         | 4 - 7  | LAST_FRAME_ID / FRAME_ID | Either the id of the last frame in the packet or the current id (most significant nibble) |
| 1       |        | LAST_FRAME_ID / FRAME_ID | Either the id of the last frame in the packet or the current id (least significant byte)  |
| 2       |        | DEVICE_ADDRESS           | Receiving device's address (most significant byte)                                        |
| 3       |        | DEVICE_ADDRESS           | Receiving device's address (least significant byte)                                       |
| 4       |        | DATA_LEN                 | Length of the data portion of the frame                                                   |
| 5 - 12  |        | DATA                     | Frame data                                                                                |
