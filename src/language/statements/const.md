# `const` Statement
A `const` statement in `ross-dsl` declares a constant [literal](../LITERAL.md). It cannot be modified and, in the parsing stage, is simply inserted in the places it's used.

## Example
Here we declare two constants and set them to the address of the device itself and some other device respectively. We later use the constant to match against it. This example forwards button pressed events to another device:
```
const device_address = 0x0001~u16;
const receiver_address = 0x0002~u16;

send BUTTON_PRESSED_EVENT_CODE from device_address to receiver_address;
```
