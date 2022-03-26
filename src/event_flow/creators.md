# Creators
Creators take a [packet](../data_handling/packets.md) and the [state](../data_handling/state.md) manager and return a new packet. Each creator contains an [extractor](./extractors.md), a [filter](./filters.md) and an optional [matcher](./matchers.md). The producer is only executed if the optional matcher returns true.
