# Elements + Simplicity

Sidechains benefit from Simplicity similar to rollups: It enables better scripting, new cryptography, better front-ends and formal verification.

Simplicity is designed to work with Elements and Liquid, so the two work especially well together. All Elements opcodes have Simplicity equivalents, including introspection. Assets work in Simplicity and it can be used in confidential transactions.

We are currently working on merging a Simplicity interpreter into Elements Core. It will be integrated as a tap leaf with a special version.

## New Tools

We have been working on better tools to work with Simplicity.

The latest addition is [tappy](https://github.com/uncomputable/tappy): a developer-friendly descriptor wallet that speaks Taproot (only). It supports Bitcoin Core, Elements Core, and Elements Core with Simplicity. For Simplicity I had to invent descriptors, which are currently based on Miniscript Policy. A lot of this is work in progress, but you can spend from Simplicity outputs on Elements Core!

### Simplicity Descriptors

| Descriptor    | Explanation  |
| ------------- | ------------ |
| TRIVIAL       | Anyone can spend |
| UNSATISFIABLE | No one can spend |
| pk(K)         | Public key K (32-byte x-only) can spend |
| sha256(H)     | Image H (32 bytes) can spend |
| after(n)      | Absolute timelock of height n |
| older(n)      | Relative timelock of height n |
| and(X, Y)     | Spend if X and Y can spend |
| or(X, Y)      | Spend if X or Y can spend |
| thresh(k, X, Y, ...) | Spend if k many of X, Y, ... can spend |
