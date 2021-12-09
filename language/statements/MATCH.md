# `match` Statement
A `match` statement in `ross-dsl` declares a [matcher](../../event_generation/MATCHERS.md).

## Example
Here we an example matcher used for dimming. It does nothing if the state variable `total_counter` is equal to zero. If it's not zero, it sets it to zero and either does nothing else or sets the current led brightness value to the last used value or 0xff if the led is already on. This way a double click always causes the lights to turn on at full power.
```
...
do {
    ...
    match and {
        not {
            StateEqualToConstFilter(total_counter, 0x00~u16);
        },
        or {
            and {
                {
                    StateMoreThanConstFilter(total_counter, click_speed);
                },
                {
                    SetStateToConstFilter(total_counter, 0x00~u16);
                }
            },
            and {
                {
                    SetStateToConstFilter(total_counter, 0x00~u16);
                },
                or {
                    and {
                        not {
                            StateEqualToConstFilter(current_value, 0x00~u8);
                        },
                        {
                            SetStateToConstFilter(current_value, 0xff~u8);
                        }
                    },
                    and {
                        {
                            StateEqualToConstFilter(current_value, 0x00~u8);
                        },
                        {
                            SetStateToStateFilter(current_value, last_value);
                        }
                    }
                }
            }
        }
    }
    ...
}
```
