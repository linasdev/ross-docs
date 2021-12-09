# Literals
Literals are a combination of a value and a type. These two things are separated by a `~`, like this: `127~u8` - this declares an 8-bit decimal 127 value.

## Normal Literals
The normal literals include unsigned integers like `u8`, `u16` and `u32`.

## Special Literals
### Boolean
Boolean values do not require the type specified, just true/false.

### String
String values are delimited by double-quotes, like this: `"This is a string"`.
They are currently only used for cron expressions.

### RGB
RGB color literals consist of a six digit hexadecimal value preceded by a hashtag. The usual HTML color notation is used, like this: `#ff00ff` 

### RGBW
RGBW color literals consist of an eight digit hexadecimal value preceded by a hashtag. The usual HTML color notation is used with an extra two digits for the white color amount, like this: `#ff00ffab`
