# `do` Statement
A `do` statement in `ross-dsl` declares an [event processor](../../event_generation/EVENT_PROCESSORS.md) which does what a user programs it to do. All the [matchers](../../event_generation/MATCHERS.md) inside and all the fire statements are combined with AND logic to form one matcher and multiple creators with optional matchers. 

## Example
Here we have an example program that sends a bcm change brightness event with an alternating value on each button press. The `active_value` is fired half of the time and the `rest_value` is fired half of the time. The button pressed events are also always retransmitted to the receiving device:
```
let active = false;

const device_address = 0x0002~u16;
const receiver_address = 0x0003~u16;

const active_value = 0xff~u8;
const rest_value = 0x00~u8;

const led_channel = 0~u8;

do {
    match event BUTTON_PRESSED_EVENT_CODE;
    match producer device_address;
    
    match {
        FlipStateFilter(active);
    }
    
    fire {
        PacketExtractor();
        PacketProducer(receiver_address);
    }

    fire { BcmChangeBrightnessProducer(receiver_address, led_channel, active_value); } if match {
        StateEqualToConstFilter(active, true);
    }

    fire { BcmChangeBrightnessProducer(receiver_address, led_channel, rest_value); } if match {
        StateEqualToConstFilter(active, false);
    }
}
```
