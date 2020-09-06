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
```bash
    zhangyb@ubuntu:~/workspace/bulletproofs$ cargo test --verbose
           Fresh autocfg v1.0.1
           Fresh rand_core v0.4.2
           Fresh autocfg v0.1.7
           Fresh lazy_static v1.4.0
           Fresh unicode-xid v0.2.1
           Fresh cfg-if v0.1.10
           Fresh itoa v0.4.6
           Fresh semver-parser v0.7.0
           Fresh byte-tools v0.3.1
           Fresh either v1.6.0
           Fresh scopeguard v1.1.0
           Fresh cc v1.0.41
           Fresh subtle v1.0.0
           Fresh opaque-debug v0.2.3
           Fresh fake-simd v0.1.2
           Fresh arrayvec v0.5.1
           Fresh unicode-width v0.1.8
           Fresh keccak v0.1.0
           Fresh arrayref v0.3.6
           Fresh constant_time_eq v0.1.5
           Fresh zeroize v0.10.1
           Fresh same-file v1.0.6
           Fresh hex v0.3.2
           Fresh rand_core v0.3.1
           Fresh rand_jitter v0.1.4
           Fresh semver v0.9.0
           Fresh block-padding v0.1.5
           Fresh itertools v0.8.2
           Fresh itertools v0.7.11
           Fresh textwrap v0.11.0
           Fresh blake2b_simd v0.5.10
           Fresh walkdir v2.3.1
           Fresh libc v0.2.76
           Fresh byteorder v1.3.4
           Fresh serde v1.0.115
           Fresh rand_hc v0.1.0
           Fresh rand_isaac v0.1.1
           Fresh rand_xorshift v0.1.1
           Fresh typenum v1.12.0
           Fresh proc-macro2 v1.0.19
           Fresh ryu v1.0.5
           Fresh maybe-uninit v2.0.0
           Fresh rustc_version v0.2.3
           Fresh memchr v2.3.3
           Fresh bitflags v1.2.1
           Fresh crossbeam-utils v0.7.2
           Fresh memoffset v0.5.5
           Fresh num-traits v0.2.12
           Fresh rand_os v0.1.3
           Fresh num_cpus v1.13.0
           Fresh regex-automata v0.1.9
           Fresh rand_xoshiro v0.1.0
           Fresh atty v0.2.14
           Fresh generic-array v0.12.3
           Fresh quote v1.0.7
           Fresh rand_pcg v0.1.2
           Fresh rand_chacha v0.1.1
           Fresh serde_json v1.0.57
           Fresh csv-core v0.1.10
           Fresh crossbeam-channel v0.4.3
           Fresh clap v2.33.3
           Fresh crossbeam-epoch v0.8.2
           Fresh bstr v0.2.13
           Fresh digest v0.8.1
           Fresh block-buffer v0.7.3
           Fresh crypto-mac v0.7.0
           Fresh syn v1.0.39
           Fresh rand v0.6.5
           Fresh tinytemplate v1.1.0
           Fresh crossbeam-deque v0.7.3
           Fresh sha3 v0.8.2
           Fresh sha2 v0.8.2
           Fresh csv v1.1.3
           Fresh serde_derive v1.0.115
           Fresh hmac v0.7.1
           Fresh secp256k1 v0.15.5
           Fresh rayon-core v1.8.0
           Fresh cast v0.2.3
           Fresh rust-gmp v0.5.0 (https://github.com/KZen-networks/rust-gmp#a15e0ec2)
           Fresh curv v0.2.6 (https://github.com/KZen-networks/curv?tag=v0.2.6#74b34dce)
           Fresh rayon v1.4.0
           Fresh criterion-plot v0.3.1
           Fresh criterion v0.2.11
       Compiling bulletproof v1.1.0 (/home/zhangyb/workspace/bulletproofs)
         Running `rustc --crate-name bulletproof src/lib.rs --error-format=json --json=diagnostic-rendered-ansi --emit=dep-info,link -Cembed-bitcode=no -C debuginfo=2 --test -C metadata=a3ae5032f6948364 -C extra-filename=-a3ae5032f6948364 --out-dir /home/zhangyb/workspace/bulletproofs/target/debug/deps -C incremental=/home/zhangyb/workspace/bulletproofs/target/debug/incremental -L dependency=/home/zhangyb/workspace/bulletproofs/target/debug/deps --extern criterion=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcriterion-e815e1a5652fe195.rlib --extern curv=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcurv-de50352838dc3fdc.rlib --extern itertools=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libitertools-f9c0c4d2563e856a.rlib --extern serde=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde-a0930becb6c91bcb.rlib --extern serde_derive=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde_derive-9657277a275bd2e8.so -L native=/home/zhangyb/workspace/bulletproofs/target/debug/build/secp256k1-13d95966bf495f4d/out`
    error: linking with `cc` failed: exit code: 1
      |
      = note: "cc" "-Wl,--as-needed" "-Wl,-z,noexecstack" "-m64" "-Wl,--eh-frame-hdr" "-L" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.10hkcbox0tc2cw8a.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.11p33cgb52es2i1l.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.1680azyq8m2wjlsq.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.1h4vjtnivgz7dhsh.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.1pezqbwjc7uqauhq.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.1v25yl4d7e2vgscu.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.1xztw0urptjgfmh9.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.21tj8gwiewkfsrp0.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.2btw5rh3lqbvysf.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.2dg8q8e26rwaemdf.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.2qb4yq6b215yswyi.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.2uuu7yo8ad4uyz12.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.2wwulhmdqrk794zo.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.2zchtvidwh30eh5v.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.31a0v5k6gh8mvjwf.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.31f9c8vr18f1uf0u.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.38gl0qk6i1jco3sr.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3dvkshiun8wg8o2s.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3f618nyoy592aocz.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3gap06t4qgd9pj9p.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3gno1mp04chnqiqk.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3hjbo7s4gxw1afsp.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3iv01u9uo72lyv6g.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3j0fmohkyq0u3iyt.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3lke7zyedcjeq7xy.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3r378i9tq9t8xcwj.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3sswbuyhzn8tyod2.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3sw8v0r8rcspiaee.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3t8sttlam5bn26a4.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.3zl78f65qzgzk857.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.485n3was47xxdtvl.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.48gocfbtoppzwf9l.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.49womvq8gua6u3uh.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4fx38qcekcq0euau.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4g9m8nhg84wc75ix.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4iag5v61iuxe9wth.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4is5ud7ts989nefl.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4og0fpqbwpzwpxpw.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4oxlyg2swp03ydxx.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4r1ntautnibnakm8.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4sge97w895wj9mz4.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.50rkbn6nkpafedzf.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.525oswsyi0y98pzs.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.58eq7tycda55o2bw.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5auwsu18v9h7s7bx.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5bmx8xgdvtccsgqm.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5di8vovvnjb2ih8x.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5eqngxlvxyzc9abs.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5fhrzx1wjcfxfka4.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5fn7tk1anw42aeup.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.5jsgmhitdszuh6z.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.ad8nca2jrzs4v7w.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.aqzvp05vwxp131q.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.g5hedaxchrw0sty.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.js1ue2vcgc8wjf6.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.o2gypx9rhxlxey.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.oexyxu8zvott8yb.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.t4af4ydfezgqhac.rcgu.o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.u27offc1oygzfl9.rcgu.o" "-o" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364.4jhn15x9v3au3kfk.rcgu.o" "-Wl,--gc-sections" "-pie" "-Wl,-zrelro" "-Wl,-znow" "-nodefaultlibs" "-L" "/home/zhangyb/workspace/bulletproofs/target/debug/deps" "-L" "/home/zhangyb/workspace/bulletproofs/target/debug/build/secp256k1-13d95966bf495f4d/out" "-L" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib" "-Wl,-Bstatic" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libtest-94bb32460f7582ad.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libterm-4cb8a8d7b46e1531.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libgetopts-6779ec9d48943b28.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libunicode_width-a177db9917f827e4.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/librustc_std_workspace_std-d2dadbfac12677fc.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libitertools-f9c0c4d2563e856a.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libeither-62e13503f7221866.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcurv-de50352838dc3fdc.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libhmac-cbdf24ee64d9760c.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcrypto_mac-15f4514674ba832e.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libsubtle-7b216bcc425fbedb.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libsha2-06616789022e7687.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libfake_simd-09dd8b6dcc873300.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libblake2b_simd-7411c23886191774.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libconstant_time_eq-49cc9a53ecf7241d.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libarrayvec-7d8a79fd9fe75dde.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libarrayref-4637e9bd81ee5669.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libsha3-c2c364e520b137aa.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libdigest-d19d508b7646aa89.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libopaque_debug-7f894d8bc75003fa.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libblock_buffer-a89259c25b317a44.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libgeneric_array-c9c7955a507180e9.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libtypenum-50a5864b187f3226.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libblock_padding-8726a7a26f88bc51.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libbyte_tools-cbfdd52d4db98f7b.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libbyteorder-bfa58b45c454d4e3.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libkeccak-8c91501e410c3c94.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libgmp-da092f99dbafd9eb.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde_json-4e526e6e34fdfafa.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libryu-3f150dffae0a8f73.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libitoa-abe2dc6bb5ac4c76.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libnum_traits-8b68808afc73958f.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libzeroize-45c8fb4e9618e46c.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libsecp256k1-5953b060d1107dd7.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand-3bcda651593771b3.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_xorshift-d88e217e37c7071c.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_pcg-a330aaf988d36df8.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_hc-346d7251dbd63068.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_chacha-f1b1b69248e6bae6.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_isaac-cbd3c355e926b13a.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_core-6ec3c7eaecdb3c02.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_os-38853ca3b3002651.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/liblibc-3b067de2f719f3b2.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_jitter-71009a1d892d8976.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/librand_core-28f0dfc5ff97706d.rlib" "/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde-a0930becb6c91bcb.rlib" "-Wl,--start-group" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libstd-cf0f33af3a901778.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libpanic_unwind-daf8c2d692e6eca4.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libhashbrown-24e8f97647425e48.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/librustc_std_workspace_alloc-85ed7d2b484c05a9.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libbacktrace-89de2c581262ec09.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libbacktrace_sys-3b0db98e62ed7d75.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/librustc_demangle-c60847f9a163de82.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libunwind-0bb9b63424f4fc5d.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libcfg_if-3f74d829e37fa40e.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/liblibc-0e9d83ff06f1a7ad.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/liballoc-2c8c904efaf7c40b.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/librustc_std_workspace_core-cbfb51de52131460.rlib" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libcore-97497c26fddb7882.rlib" "-Wl,--end-group" "/home/zhangyb/.rustup/toolchains/stable-x86_64-unknown-linux-gnu/lib/rustlib/x86_64-unknown-linux-gnu/lib/libcompiler_builtins-f1a9d8c443e20b5e.rlib" "-Wl,-Bdynamic" "-lgmp" "-lgmp" "-lgmp" "-lgmp" "-lgmp" "-lutil" "-ldl" "-lutil" "-ldl" "-lrt" "-lpthread" "-lgcc_s" "-lc" "-lm" "-lrt" "-lpthread" "-lutil" "-ldl" "-lutil"
      = note: /usr/bin/ld: cannot find -lgmp
              /usr/bin/ld: cannot find -lgmp
              /usr/bin/ld: cannot find -lgmp
              /usr/bin/ld: cannot find -lgmp
              /usr/bin/ld: cannot find -lgmp
              collect2: error: ld returned 1 exit status


    error: aborting due to previous error

    error: could not compile `bulletproof`.

    Caused by:
      process didn't exit successfully: `rustc --crate-name bulletproof src/lib.rs --error-format=json --json=diagnostic-rendered-ansi --emit=dep-info,link -Cembed-bitcode=no -C debuginfo=2 --test -C metadata=a3ae5032f6948364 -C extra-filename=-a3ae5032f6948364 --out-dir /home/zhangyb/workspace/bulletproofs/target/debug/deps -C incremental=/home/zhangyb/workspace/bulletproofs/target/debug/incremental -L dependency=/home/zhangyb/workspace/bulletproofs/target/debug/deps --extern criterion=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcriterion-e815e1a5652fe195.rlib --extern curv=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcurv-de50352838dc3fdc.rlib --extern itertools=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libitertools-f9c0c4d2563e856a.rlib --extern serde=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde-a0930becb6c91bcb.rlib --extern serde_derive=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde_derive-9657277a275bd2e8.so -L native=/home/zhangyb/workspace/bulletproofs/target/debug/build/secp256k1-13d95966bf495f4d/out` (exit code: 1)
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
```bash
    zhangyb@ubuntu:~/workspace/bulletproofs$ cargo test --verbose
       Fresh autocfg v1.0.1
       Fresh rand_core v0.4.2
       Fresh autocfg v0.1.7
       Fresh lazy_static v1.4.0
       Fresh unicode-xid v0.2.1
       Fresh semver-parser v0.7.0
       Fresh cfg-if v0.1.10
       Fresh itoa v0.4.6
       Fresh either v1.6.0
       Fresh byte-tools v0.3.1
       Fresh cc v1.0.41
       Fresh scopeguard v1.1.0
       Fresh opaque-debug v0.2.3
       Fresh subtle v1.0.0
       Fresh fake-simd v0.1.2
       Fresh arrayvec v0.5.1
       Fresh unicode-width v0.1.8
       Fresh constant_time_eq v0.1.5
       Fresh arrayref v0.3.6
       Fresh keccak v0.1.0
       Fresh zeroize v0.10.1
       Fresh same-file v1.0.6
       Fresh hex v0.3.2
       Fresh rand_core v0.3.1
       Fresh rand_jitter v0.1.4
       Fresh semver v0.9.0
       Fresh block-padding v0.1.5
       Fresh itertools v0.8.2
       Fresh itertools v0.7.11
       Fresh textwrap v0.11.0
       Fresh blake2b_simd v0.5.10
       Fresh walkdir v2.3.1
       Fresh libc v0.2.76
       Fresh byteorder v1.3.4
       Fresh rand_isaac v0.1.1
       Fresh rand_hc v0.1.0
       Fresh rand_xorshift v0.1.1
       Fresh typenum v1.12.0
       Fresh serde v1.0.115
       Fresh proc-macro2 v1.0.19
       Fresh ryu v1.0.5
       Fresh maybe-uninit v2.0.0
       Fresh rustc_version v0.2.3
       Fresh memchr v2.3.3
       Fresh bitflags v1.2.1
       Fresh crossbeam-utils v0.7.2
       Fresh memoffset v0.5.5
       Fresh num-traits v0.2.12
       Fresh rand_os v0.1.3
       Fresh num_cpus v1.13.0
       Fresh regex-automata v0.1.9
       Fresh rand_xoshiro v0.1.0
       Fresh atty v0.2.14
       Fresh generic-array v0.12.3
       Fresh rand_chacha v0.1.1
       Fresh rand_pcg v0.1.2
       Fresh quote v1.0.7
       Fresh serde_json v1.0.57
       Fresh csv-core v0.1.10
       Fresh clap v2.33.3
       Fresh crossbeam-epoch v0.8.2
       Fresh crossbeam-channel v0.4.3
       Fresh bstr v0.2.13
       Fresh digest v0.8.1
       Fresh block-buffer v0.7.3
       Fresh crypto-mac v0.7.0
       Fresh syn v1.0.39
       Fresh rand v0.6.5
       Fresh tinytemplate v1.1.0
       Fresh crossbeam-deque v0.7.3
       Fresh csv v1.1.3
       Fresh serde_derive v1.0.115
       Fresh hmac v0.7.1
       Fresh sha3 v0.8.2
       Fresh sha2 v0.8.2
       Fresh secp256k1 v0.15.5
       Fresh cast v0.2.3
       Fresh rayon-core v1.8.0
       Fresh rust-gmp v0.5.0 (https://github.com/KZen-networks/rust-gmp#a15e0ec2)
       Fresh criterion-plot v0.3.1
       Fresh rayon v1.4.0
       Fresh curv v0.2.6 (https://github.com/KZen-networks/curv?tag=v0.2.6#74b34dce)
       Fresh criterion v0.2.11
    Compiling bulletproof v1.1.0 (/home/zhangyb/workspace/bulletproofs)
     Running `rustc --crate-name bulletproof src/lib.rs --error-format=json --json=diagnostic-rendered-ansi --emit=dep-info,link -Cembed-bitcode=no -C debuginfo=2 --test -C metadata=a3ae5032f6948364 -C extra-filename=-a3ae5032f6948364 --out-dir /home/zhangyb/workspace/bulletproofs/target/debug/deps -C incremental=/home/zhangyb/workspace/bulletproofs/target/debug/incremental -L dependency=/home/zhangyb/workspace/bulletproofs/target/debug/deps --extern criterion=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcriterion-e815e1a5652fe195.rlib --extern curv=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcurv-de50352838dc3fdc.rlib --extern itertools=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libitertools-f9c0c4d2563e856a.rlib --extern serde=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde-a0930becb6c91bcb.rlib --extern serde_derive=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde_derive-9657277a275bd2e8.so -L native=/home/zhangyb/workspace/bulletproofs/target/debug/build/secp256k1-13d95966bf495f4d/out`
    Finished test [unoptimized + debuginfo] target(s) in 8.11s
     Running `/home/zhangyb/workspace/bulletproofs/target/debug/deps/bulletproof-a3ae5032f6948364`

    running 39 tests
    test proofs::inner_product::tests::make_ipp_1_fast_verify ... ok
    test proofs::inner_product::tests::make_ipp_1 ... ok
    test proofs::inner_product::tests::make_ipp_2 ... ok
    test proofs::inner_product::tests::make_ipp_2_fast_verify ... ok
    test proofs::inner_product::tests::make_ipp_16_fast_verify ... ok
    test proofs::inner_product::tests::make_ipp_16 ... ok
    test proofs::inner_product::tests::make_ipp_4_fast_verify ... ok
    test proofs::inner_product::tests::make_ipp_4 ... ok
    test proofs::inner_product::tests::make_ipp_8_fast_verify ... ok
    test proofs::inner_product::tests::make_ipp_8 ... ok
    test proofs::inner_product::tests::make_ipp_32_fast_verify ... ok
    test proofs::inner_product::tests::make_ipp_32 ... ok
    test proofs::inner_product::tests::make_ipp_non_power_2 ... ok
    test proofs::range_proof::tests::test_batch_1_range_proof_8 ... ok
    test proofs::range_proof::tests::test_batch_2_range_proof_16 ... ok
    test proofs::range_proof::tests::test_batch_4_range_proof_32_out_of_range ... ok
    test proofs::range_proof::tests::test_batch_4_range_proof_32 ... ok
    test proofs::range_proof_wip::tests::test_batch_1_wip_range_proof_8 ... ok
    test proofs::range_proof_wip::tests::test_batch_2_wip_range_proof_16 ... ok
    test proofs::range_proof::tests::test_agg_batch_4_range_proof_64 ... ok
    test proofs::range_proof_wip::tests::test_batch_4_wip_range_proof_32 ... ok
    test proofs::range_proof_wip::tests::test_batch_4_wip_range_proof_32_out_of_range ... ok
    test proofs::weighted_inner_product::tests::make_wip_1 ... ok
    test proofs::weighted_inner_product::tests::make_wip_16 ... ok
    test proofs::range_proof::tests::test_batch_4_range_proof_64 ... ok
    test proofs::weighted_inner_product::tests::make_wip_1_fast_verify ... ok
    test proofs::weighted_inner_product::tests::make_wip_2 ... ok
    test proofs::weighted_inner_product::tests::make_wip_2_fast_verify ... ok
    test proofs::weighted_inner_product::tests::make_wip_16_fast_verify ... ok
    test proofs::weighted_inner_product::tests::make_wip_32 ... ok
    test proofs::weighted_inner_product::tests::make_wip_32_fast_verify ... ok
    test proofs::weighted_inner_product::tests::make_wip_4 ... ok
    test proofs::weighted_inner_product::tests::make_wip_4_fast_verify ... ok
    test proofs::weighted_inner_product::tests::make_wip_8 ... ok
    test proofs::weighted_inner_product::tests::make_wip_8_fast_verify ... ok
    test proofs::weighted_inner_product::tests::test_wip ... ok
    test proofs::weighted_inner_product::tests::make_wip_non_power_2 ... ok
    test proofs::range_proof_wip::tests::test_batch_4_wip_range_proof_64 ... ok
    test proofs::range_proof_wip::tests::test_batch_agg_4_wip_range_proof_64 ... ok

    test result: ok. 39 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out

    Doc-tests bulletproof
     Running `rustdoc --crate-type lib --test /home/zhangyb/workspace/bulletproofs/src/lib.rs --crate-name bulletproof -L dependency=/home/zhangyb/workspace/bulletproofs/target/debug/deps -L dependency=/home/zhangyb/workspace/bulletproofs/target/debug/deps -L native=/home/zhangyb/workspace/bulletproofs/target/debug/build/secp256k1-13d95966bf495f4d/out --extern bulletproof=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libbulletproof-9e0c96a462a1239d.rlib --extern criterion=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcriterion-e815e1a5652fe195.rlib --extern curv=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libcurv-de50352838dc3fdc.rlib --extern itertools=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libitertools-f9c0c4d2563e856a.rlib --extern serde=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde-a0930becb6c91bcb.rlib --extern serde_derive=/home/zhangyb/workspace/bulletproofs/target/debug/deps/libserde_derive-9657277a275bd2e8.so`

    running 0 tests

    test result: ok. 0 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out
```

# Opensource Resources (repos and docs)
## ZenGo-X bulletproofs
``` console
https://github.com/ZenGo-X/bulletproofs.git
```
## dalek-cryptography bulletproofs (only works on branch develop, verified on 2020-09-05 12:06:00)
``` console
https://github.com/dalek-cryptography/bulletproofs.git
```

## OSCCA SM2/3/4 implementation in Rust
``` console
https://github.com/citahub/libsm.git
```

## Documents
- [Getting start with QEMU](https://rust-embedded.github.io/book/start/qemu.html)
- [the embedded Rust book](https://rust-embedded.github.io/book/)
- [RFC-1184](https://github.com/rust-lang/rfcs/blob/master/text/1184-stabilize-no_std.md)
- [embedonomicon](https://docs.rust-embedded.org/embedonomicon/smallest-no-std.html)
- [More about the language items](https://doc.rust-lang.org/unstable-book/language-features/lang-items.html#more-about-the-language-items)
- [How to use compiled rust library file(.rlib file)](https://users.rust-lang.org/t/how-to-use-compiled-rust-library-file-rlib-file/17484)
