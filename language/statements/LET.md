# `let` Statement
A `let` statement in `ross-dsl` declares a [state](../../data_handling/STATE.md) variable. It can be modified by state modifying filters and can be used for both matching and event production.

## Example
Here we declare a state variable and set it equal to false. We later change this variable on button pressed and button released events. This maintains the current state of a button input:
```
let button_pressed = false;

const device_address = 0x0001~u16;
const button_index = 0~u8;

set button_pressed to true on BUTTON_PRESSED_EVENT_CODE from device_address if match {
    ButtonIndexExtractor();
    ValueEqualToConstFilter(button_index);
}

set button_pressed to false on BUTTON_PRESSED_EVENT_CODE from device_address if match {
    ButtonIndexExtractor();
    ValueEqualToConstFilter(button_index);
}
```
