# Creators
Creators take a [packet](../data_handling/PACKETS.md) and the [state](../data_handling/STATE.md) manager and return a new packet. Each creator contains an [extractor](EXTRACTORS.md), a [filter](FILTERS.md) and an optional [matcher](MATCHERS.md). The producer is only executed if the optional matcher returns true.
