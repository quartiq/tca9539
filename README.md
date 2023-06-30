# `tca9539`

This crate is a `no_std` driver for the
[TCA9539](https://www.ti.com/product/TCA9539) and
[PCA9539](https://www.nxp.com/docs/en/data-sheet/PCA9539_PCA9539R.pdf)
16-Bit/8-Bit I2C I/O Expanders.

[![Build Status](https://github.com/quartiq/tca9539/actions/workflows/ci.yml/badge.svg)](https://github.com/quartiq/tca9539/actions?query=workflow%3Aci)
[![crates.io](https://img.shields.io/crates/v/tca9539.svg)](https://crates.io/crates/tca9539)
[![Docs](https://docs.rs/tca9539/badge.svg)](https://docs.rs/tca9539)

## Basic usage

Include this [library](https://crates.io/crates/tca9539) as a dependency in your `Cargo.toml`:

```rust
[dependencies]
tca9539 = "0.1"
```

Use [embedded-hal](https://github.com/rust-embedded/embedded-hal) implementation to get I2C handle and then create chip handle:

```rust
use tca9539::*;

let pin = Pin::P13;
let mut u = Tca9539<I2C>::default(i2c).unwrap();
u.set_direction(pin, Direction::Output).unwrap();
u.set_level(pin, Level::High).unwrap();
assert!(u.gpio(pin).unwrap());
```

## Documentation

API Docs available on [docs.rs](https://docs.rs/tca9539)

Minimum supported Rust version (MSRV) is 1.62.0.

## License

[MIT license](http://opensource.org/licenses/MIT)
