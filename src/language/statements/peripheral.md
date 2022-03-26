# `peripheral` Statement
A `peripheral` statement in `ross-dsl` declares a peripheral and its type. BCM and relay devices require the used peripherals to be specified explicitly.

## Example
Here we declare the device's peripherals to be one single channel BCM output at index 0 and one RGBW BCM output at index 1:
```
peripheral 0x00~u32 bcm single(0x00~u8);
peripheral 0x01~u32 bcm rgbw(0x01~u8, 0x02~u8, 0x03~u8, 0x04~u8);
```
