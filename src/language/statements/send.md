# `send` Statement
A `send` statement in `ross-dsl` declares an [event processor](../../event_generation/EVENT_PROCESSORS.md) which forwards specific events from one address to another. It matches against the event code and producer device's address. The extended syntax supports an additional [matcher](../../event_generation/MATCHERS.md).

## Example
Here we forward all button pressed events to one device and only events with a specific button index to another device:
```
const device_address = 0x0001~u16;
const receiver_address1 = 0x0002~u16;
const receiver_address2 = 0x0003~u16;
const button_index = 0~u8;

send BUTTON_PRESSED_EVENT_CODE from device_address to receiver_address1;
send BUTTON_PRESSED_EVENT_CODE from device_address to receiver_address2 if match {
    ButtonIndexExtractor();
    ValueEqualToConstFilter(button_index);
}
```
