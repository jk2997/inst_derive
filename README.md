[![Docs](https://img.shields.io/badge/docs-0.1.1-green)](https://docs.rs/inst_derive/latest/inst_derive/)
[![crates.io](https://img.shields.io/badge/crates.io-0.1.1-green)](https://crates.io/crates/inst_derive)

## Description

Derive macro for the Instantiable trait in [safety-net](https://github.com/matth2k/safety-net).

Makes it easier to group Instantiable structs into a single enum.

## Example

Use the `#[instantiable(constant)]` attribute on a variant to specify which variant should be used for `from_constant()`. The variant must have a `pub fn from_constant(val: Logic) -> Option<Self>` method that returns an Option of the variant type.

```rust
use inst_derive::Instantiable;
use safety_net::{Gate, Identifier, Instantiable, Logic, Net, Parameter};
#[derive(Debug, Clone, Instantiable)]
enum Cell {
    #[instantiable(constant)]
    Gate(Gate),
    // additional variants
}
```

