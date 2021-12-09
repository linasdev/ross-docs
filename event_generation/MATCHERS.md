# Matchers
Matchers take some [extracted](EXTRACTORS.md) value and the [state](../data_handling/STATE.md) manager and return a true/false value. They can be combined to form a tree of matchers. Each matcher contains an extractor and a [filter](FILTERS.md). The filters can be state modifying, this is required to form advanced logic that requires awareness of current state.

## Combinational logic
`ross-dsl` has combinational logic features with `not`, `and` and `or` operators. All of the operators are short-circuiting, meaning if an expression can be evaluated lazily, it will be. This is important when it comes to state modifying filters, because we can build if-else like logic.
