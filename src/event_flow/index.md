# Event flow
Inside a ross system events have a specific flow. On each receiving device it is run against many [event processors](./event_processors.md), which in turn contain a [matcher](./matchers.md), composed of an [extractor](./extractors.md) and a [filter](./filters.md), and many [creators](./creators.md), composed of an extractor, a [producer](./producers.md) and an optional matcher.
