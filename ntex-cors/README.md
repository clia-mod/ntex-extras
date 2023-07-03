<div align="center">

# A mod to ntex-cors

It doesn't require an 'ORIGIN' header to produce CORS header.

[![Version](https://img.shields.io/badge/rustc-1.65+-lightgray.svg)](https://blog.rust-lang.org/2022/11/03/Rust-1.65.0.html) 
[![codecov](https://codecov.io/gh/ntex-rs/ntex-extras/branch/master/graph/badge.svg)](https://codecov.io/gh/ntex-rs/ntex-extras) 

</div>

## Documentation & community resources

* [User Guide](https://ntex.rs/docs)
* [API Documentation](https://docs.rs/ntex-cors/)
* Cargo package: [ntex-cors](https://crates.io/crates/ntex-cors)
* Minimum supported Rust version: 1.65 or later

## A loose config example

```toml
ntex-cors = { package = "clia-ntex-cors-mod", version = "0.4" }
```

```rust
.wrap(
    Cors::new()
        .allowed_methods(vec![
            "GET", "HEAD", "POST", "OPTIONS", "PUT", "PATCH", "DELETE",
        ])
        .send_wildcard()
        .finish(),
)
```

Will produce CORS headers for every request:

```http
vary: Origin
access-control-allow-origin: *
```

## Build statuses

| Platform         | Build Status |
| ---------------- | ------------ |
| Linux            | [![build status](https://github.com/ntex-rs/ntex-extras/workflows/CI%20%28Linux%29/badge.svg?branch=master&event=push)](https://github.com/ntex-rs/ntex-extras/actions?query=workflow%3A"CI+(Linux)") |
| macOS            | [![build status](https://github.com/ntex-rs/ntex-extras/workflows/CI%20%28OSX%29/badge.svg?branch=master&event=push)](https://github.com/ntex-rs/ntex-extras/actions?query=workflow%3A"CI+(OSX)") |
| Windows          | [![build status](https://github.com/ntex-rs/ntex-extras/workflows/CI%20%28Windows%29/badge.svg?branch=master&event=push)](https://github.com/ntex-rs/ntex-extras/actions?query=workflow%3A"CI+(Windows)") |
