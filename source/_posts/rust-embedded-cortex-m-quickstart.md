---
title: Rust-embedded Cortex-M-Quickstart
date: 2020-09-03 19:35:45
updated: 2020-09-03 19:35:45
categories:
  - [Rust]
tags:
  - Cortex M
  - Rust
  - Embedded
mathjax: false
---

## Introduction
To run Rust programs in Cortex M core. Guide could be found [here](https://rust-embedded.github.io/book/intro/index.html).

## Git repos
- [cortex-m-quickstart](https://github.com/rust-embedded/cortex-m-quickstart.git)

## Dependencies
``` bash
cargo install cargo-binutils
rustup component add llvm-tools-preview  #lack of this tools will result in Failed to execute tool: readobj
```
Dependencies could be find [here](https://docs.rust-embedded.org/discovery/03-setup/index.html).
