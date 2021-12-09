# Extractors
Extractors take a [packet](../data_handling/PACKETS.md) and extract some arbitrary information later to be used in a [filter](FILTERS.md) or a [producer](PRODUCERS.md).

## Extractor Types
`Ross` currently uses the following extractor types:

| Extractor Code | Extractor syntax in `ross-dsl`     | Description                                                              |
|----------------|------------------------------------|--------------------------------------------------------------------------|
| 0x0000         | `NoneExtractor();`                 | Extracts nothing from the packet                                         |
| 0x0001         | `PacketExtractor();`               | Extracts the whole packet (used with a packet producer)                  |
| 0x0002         | `EventCodeExtractor();`            | Extracts the [event](../data_handling/EVENTS.md) code from the packet    |
| 0x0003         | `EventProducerAddressExtractor();` | Extracts the transmitter address from the packet                         |
| 0x0004         | `MessageCodeExtractor();`          | Extracts a user defined message code from a message event                |
| 0x0005         | `MessageValueExtractor();`         | Extracts a user defined value from a message event                       |
| 0x0006         | `ButtonIndexExtractor();`          | Extracts the button index from a button pressed or button released event |
