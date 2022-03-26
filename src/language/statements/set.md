# `set` Statement
A `set` statement in `ross-dsl` declares an [event processor](../../event_generation/EVENT_PROCESSORS.md) which sets some state variable to a constant (state variables will be supported later) on some specific event. It matches against the event code and producer device's address. The extended syntax supports an additional [matcher](../../event_generation/MATCHERS.md).

## Example
Here we declare a state variable and set it equal to false. We later change this variable on button pressed and button released events. This maintains the current state of a specific button and if any button was pressed:
```
let button_pressed = false;
let any_button_pressed = false;

const device_address = 0x0001~u16;
const button_index = 0~u8;

set any_button_pressed to true on BUTTON_PRESSED_EVENT_CODE from device_address;
set button_pressed to true on BUTTON_PRESSED_EVENT_CODE from device_address if match {
    ButtonIndexExtractor();
    ValueEqualToConstFilter(button_index);
}

set any_button_pressed to false on BUTTON_RELEASED_EVENT_CODE from device_address;
set button_pressed to false on BUTTON_RELEASED_EVENT_CODE from device_address if match {
    ButtonIndexExtractor();
    ValueEqualToConstFilter(button_index);
}
```
