# Filters
Filters take an [extracted](EXTRACTORS.md) value and the [state](../data_handling/STATE.md) manager and return a true/false value.
Certain filters can modify the device's global state. The state is updated immediately for the next filters to use.

## Filter Types
`Ross` currently uses the following filter types:

| Filter Code | Filter syntax in `ross-dsl`                     | Description                                           |
|-------------|-------------------------------------------------|-------------------------------------------------------|
| 0x0000      | `ValueEqualToConstFilter(const);`               | Compares extracted value with a constant              |
| 0x0001      | `StateEuqlToConstFilter(state, const);`         | Compares a state variable with a constant             |
| 0x0002      | `StateEqualToValueFilter(state);`               | Compares a state variable with an extracted value     |
| 0x0003      | `IncrementStateByConstFilter(state, const);`    | Increments a state variable by a constant             |
| 0x0004      | `IncrementStateByValueFilter(state);`           | Increments a state variable by an extracted value     |
| 0x0005      | `DecrementStateByConstFilter(state, const);`    | Decrements a state variable by a constant             |
| 0x0006      | `DecrementStateByValueFilter(state);`           | Decrements a state variable by an extracted value     |
| 0x0007      | `SetStateToConstFilter(state, const);`          | Sets a state variable to a constant                   |
| 0x0008      | `SetStateToValueFilter(state);`                 | Sets a state variable to an extracted value           |
| 0x0009      | `FlipStateFilter(state);`                       | Flips a boolean state variable                        |
| 0x000a      | `TimeMatchesCronExpressionFilter(expression);`  | Compares the current time with a cron expression      |
| 0x000b      | `StateMoreThanConstFilter(state, const);`       | Compares a state variable with a constant             |
| 0x000c      | `StateLessThanConstFilter(state, const);`       | Compares a state variable with a constant             |
| 0x000d      | `SetStateToStateFilter(state, target_state);`   | Sets a state variable to another state variable       |
| 0x000e      | `StateEqualToStateFilter(state, target_state);` | Compares a state variable with another state variable |
