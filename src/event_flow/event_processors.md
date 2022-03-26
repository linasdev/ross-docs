# Event Processors
Event processors take a [packet](../data_handling/packets.md) and the [state](../data_handling/state.md) manager, modify the state and return a list of packets. Each event processor contains a [matcher](./matchers.md) and some a list of [creators](./creators.md). All creators are attempted if the initial matcher returns true.
