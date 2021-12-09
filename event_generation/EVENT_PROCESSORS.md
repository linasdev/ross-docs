# Event Processors
Event processors take a [packet](../data_handling/PACKETS.md) and the [state](../data_handling/STATE.md) manager, modify the state and return a list of packets. Each event processor contains a [matcher](MATCHERS.md) and some a list of [creators](CREATORS.md). All creators are attempted if the initial matcher returns true.
