# Events
Events are specific bundles of data with different formats. Everything in `ross` devices happens on some kind of event and events are generated when something happens.

## Event Types
`Ross` currently uses the following event types:

| Event Code | Event syntax in `ross-dsl`                     | Description                                                          |
|------------|------------------------------------------------|----------------------------------------------------------------------|
| 0x0000     | `BOOTLOADER_HELLO_EVENT_CODE`                  | Event transmitted in response to a PROGRAMMER_HELLO event            |
| 0x0001     | `PROGRAMMER_HELLO_EVENT_CODE`                  | Event transmitted in order to find active devices in the network     |
| 0x0002     | `PROGRAMMER_START_FIRMWARE_UPGRADE_EVENT_CODE` | Event containing firmware upgrade information                        |
| 0x0003     | `ACK_EVENT_CODE`                               | Event containing an acknowledgement                                  |
| 0x0004     | `DATA_EVENT_CODE`                              | Event containing arbitrary data                                      |
| 0x0005     | `CONFIGURATOR_HELLO_EVENT_CODE`                | Event transmitted in order to find an active `programmer` device     |
| 0x0006     | `BCM_CHANGE_BRIGHTNESS_EVENT_CODE`             | Devices with BCM outputs react to this event and change their state  |
| 0x0007     | `BUTTON_PRESSED_EVENT_CODE`                    | Devices with button inputs generate this event on button press       |
| 0x0008     | `BUTTON_RELEASED_EVENT_CODE`                   | Devices with button inputs generate this event on button release     |
| 0x0009     | `INTERNAL_SYSTEM_TICK_EVENT_CODE`              | Internal event which is fired every 1 millisecond                    |
| 0x000a     | `PROGRAMMER_START_CONFIG_UPGRADE_EVENT_CODE`   | Event containing config upgrade information                          |
| 0x000b     | `PROGRAMMER_SET_DEVICE_ADDRESS_EVENT_CODE`     | Event containing a new device address                                |
| 0x000c     | `MESSAGE_EVENT_CODE`                           | User defined event containing a user defined code and value          |
| 0x000d     | `BCM_ANIMATE_BRIGHTNESS_EVENT_CODE`            | Devices with BCM outputs react to this event and animate their state |
| 0x000e     | `RELAY_SET_STATE_EVENT_CODE`                   | Device with relay outputs react to this event and change their state |
| 0x000f     | `RELAY_FLIP_STATE_EVENT_CODE`                  | Device with relay outputs react to this event and flip their state   |
