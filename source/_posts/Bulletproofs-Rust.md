---
title: Error on building Bulletproofs
date: 2020-09-02 23:31:23
updated: 2020-09-06 22:50:53
categories:
  - [Rust]
tags:
  - Zero Knowledge Proof
  - Rust
  - Bulletproofs
mathjax: false
---
# Download the code.
Clone code from [GitHub](https://github.com/ZenGo-X/bulletproofs.git).
```bash
git clone https://github.com/ZenGo-X/bulletproofs.git
```
# Build follow the README.md

# Error found as below.
```text
$ cargo test --verbose
       Compiling bulletproof v1.1.0
    error: linking with `cc` failed: exit code: 1
      |
      = note: /usr/bin/ld: cannot find -lgmp    <!-- The root cause -->
              collect2: error: ld returned 1 exit status

    error: aborting due to previous error
    error: could not compile `bulletproof`.
```
# Solution
The key issue is
```bash
/usr/bin/ld: cannot find -lgmp
```
Then install libgmp-dev
```bash
sudo apt install libgmp-dev
```

# Done
Everything works now.
```text
$ cargo test --verbose
    Finished test [unoptimized + debuginfo] target(s) in 8.11s
     Running unittests...

    running 39 tests
    test proofs::inner_product::tests::make_ipp_1 ... ok
    test proofs::inner_product::tests::make_ipp_1_fast_verify ... ok
    test proofs::range_proof::tests::test_batch_1_range_proof_8 ... ok
    test proofs::range_proof_wip::tests::test_batch_1_wip_range_proof_8 ... ok
    test proofs::weighted_inner_product::tests::make_wip_1 ... ok
    // ... all 39 tests passed ...

    test result: ok. 39 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out
```

## Open Source Resources

- [ZenGo-X/bulletproofs](https://github.com/ZenGo-X/bulletproofs.git) — the repo used in this article
- [dalek-cryptography/bulletproofs](https://github.com/dalek-cryptography/bulletproofs.git) (branch `develop`, verified on 2020-09-05)
- [citahub/libsm](https://github.com/citahub/libsm.git) — OSCCA SM2/3/4 implementation in Rust
