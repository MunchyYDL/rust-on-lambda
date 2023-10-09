# Rust on Lambda

- Why consider Rust?
- How to use Rust on Lambda
  - Some small examples
- Useful links and resources

## Why consider Rust?

Rust is a systems programming language, which compiles to native code with really good performance.

It has some great guarantees that it can provide out of the box, if your code compiles there's a high chance that your code executes correctly as well.

It has a small std-library, which is compiled in as default, but this can also be opted out of, allowing you to create really small binaries that fits well for IoT-devices and such.

It's also a good choice for targeting WASM, as there is good tooling around that available, which can be used to target more computationally intensive tasks when running in the browser, or for developing native extensions/modules for node.

It's also a good alternative when needing to interface with C or C++, and you can build a good interface between your safe Rust code and the unsafe land of dangling pointers and segfaults that those languages comes with.

[Rust's Homepage](https://www.rust-lang.org/)

### Why Rust on AWS?

**OBS!** _Not a primary language at Polestar currently!_

Rust as a language has been used within AWS for years, but it has taken time for them to give support for developers using Rust on their platform.

_Example_: [Firecracker](https://aws.amazon.com/blogs/aws/firecracker-lightweight-virtualization-for-serverless-computing/)

The SDK has been in experimental status for ever, and now it's in alpha, but it works well enough to start using it, and it gives you about the same capabilities in general as the SDKs available for other languages.

It's also very easy to cross-compile Rust code, so you can build for the optimal target in e.g. AWS Lambda.

### Why Rust instead of lang X?

For both JS/TS and .Net you have quite the runtime to load when running your code, and the garbage collection can cause hiccups.

Rust have no need for a runtime or garbage collector, and can achieve speeds in comparison to C or C++.

In particular the native compiled Rust code produces small binaries with a bit of optimizations, and have super low cold start times on AWS Lambda.

[Lambda Cold Starts benchmark](https://maxday.github.io/lambda-perf/)

## Useful Links and Resources

**Rust at Polestar**

- Slack channel: [\#rust](https://polestardigiconnect.slack.com/archives/C051Y79EZ6X)

**Rust in general**

- Rust home - https://www.rust-lang.org
- Rust crates - https://crates.io
- Rust crates (alt) - https://lib.rs
- Rust crate documentation - https://docs.rs

**Learning Rust**

- Rustlings - https://github.com/rust-lang/rustlings
- Shuttle Launchpad - https://www.shuttle.rs/launchpad

**Rust & AWS**

- Rust on AWS - https://aws.amazon.com/developer/language/rust/
- Serverless-rust - https://www.serverless.com/plugins/serverless-rust
- AWS CDK & Rust - https://dev.to/ryands17/rust-on-lambda-using-the-cdk-3ccm

- YouTube - Serverless Rust - https://youtube.com/playlist?list=PLCOG9xkUD90KQ1IPQT_m1NbPRXXRFb63s&si=0iplAKaxlpju9E0G

**Fun Rust-related links**

- Rust and i are getting married - https://www.youtube.com/watch?v=UdE8_V05BI8
