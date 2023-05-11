# Appendix: Past Blog Posts

Posts followed by an AI-generated summary. I briefly checked the output, but there might still be errors. Take what the AI says with a grain of salt.

## 2022-11-21 From Miniscript to Simplicity

[Post](https://blog.blockstream.com/from-miniscript-to-simplicity/)

The blog post discusses how trees can be used to improve Bitcoin script and Simplicity, a new blockchain language. Miniscript, a subset of Bitcoin Script, imposes a tree structure on scripts that make it easier to statically analyze and prove properties, leading to greater confidence in the correctness of scripts. Simplicity takes this idea further and represents programs as trees that can compute arbitrary Boolean functions. It has explicit semantics, making it easy to prove properties and check for programmatic correctness. The post also discusses a bridge between Miniscript and Simplicity that will allow the conversion of Bitcoin scripts to Simplicity programs.

## 2021-08-03 Simplicity: Taproot and Universal Sighashes

[Post](https://blog.blockstream.com/simplicity-taproot-and-universal-sighashes/)

The blog post discusses the progress of the Simplicity language towards becoming production-ready and more accessible to users. The changes include an expansive set of jets that support various arithmetic and cryptographic operations, and improvements to jet encoding, static analysis, and anti-denial-of-service protection. The post also explains the concept of universal sighashes and how Simplicity's disconnect combinator enables users to delegate decisions to alternate public keys and perform a range of functions, including signing the transaction fee rate and delegating funds controlled by a specific key. The post concludes with a demonstration of creating a pair of transactions using Simplicity and new tools, including the rust-simplicity and elements-miniscript, to work with Simplicity.

## 2020-09-28 Disconnecting Simplicity Expressions

[Post](https://blog.blockstream.com/disconnecting-simplicity-expressions/)

The blog post discusses the recent implementation of the Simplicity programming language for Elements regtest network and the application of the disconnect combinator feature. Simplicity employs a Merklized Abstract Syntax Tree (MAST) similar to Bitcoin's P2SH to commit to the hash of a program. The disconnect combinator allows one part of the Simplicity program to be supplied at redemption time instead of receiving time. This feature enables several applications, such as creating a custom signature hash mode with arbitrary constraints, delegating control of funds to another public key, and creating loops without bounds. The post provides examples of each of these applications.

## 2018-11-28 Simplicity: High-Assurance Smart Contracting

[Post](https://blog.blockstream.com/en-simplicity-github/)

Blockstream has released the source code for Simplicity, a low-level programming language and machine model for blockchain-based smart contracts. The language is designed to address the challenges posed by blockchain programming languages, which typically make trade-offs between expressiveness and reliability. Simplicity is built to be compatible with Blockstream’s Elements platform, and its simplicity of semantics makes it suitable for static analysis and reasoning by formal methods. The release includes a technical report, denotational semantics, operational semantics, and an interpreter, type-checker, and serialization of the Simplicity language, as well as cryptographic primitives such as SHA-256 and EC-Schnorr signature verification. Going forward, Simplicity development will include completing the C interpreter, integrating Simplicity into the Elements blockchain platform, and building fully verified smart contracts.

## 2017-10-30 Simplicity Itself For Blockchains

[Post](https://blog.blockstream.com/en-simplicity/)

Dr. Russell O'Connor of Blockstream has developed a new blockchain programming language called Simplicity, which offers improvements over existing cryptocurrency languages such as complete expressiveness, type-safety, analyzability, and formal semantics for formal verification. Simplicity is a native Merklized Abstract Syntax Trees (MAST) programming language that increases privacy and decreases block space requirements. Simplicity is a Blockstream Research & Development project, and the next step is the release of a Simplicity SDK.