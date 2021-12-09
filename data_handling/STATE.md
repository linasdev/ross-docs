# State
`Ross` uses a dynamically allocated [B-Tree](https://en.wikipedia.org/wiki/B-tree) map to store a variety of differently typed values.

## Types
State can be of the following types:
- U8 (unsigned 8-bit integer)
- U16 (unsigned 16-bit integer)
- U32 (unsigned 32-bit integer)
- Bool (true/false value)
- Rgb (a three component (24-bit) color value)
- Rgbw (a four component (32-bit) color value)

State can also currently switch types. This can be achieved by using a `set state` filter with a different value type than the original.
