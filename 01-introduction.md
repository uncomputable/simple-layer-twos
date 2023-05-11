# Introduction + Simplicity

## What We Want

We want to express spending conditions on chain. To be precise, we want to _verify_ all Turing-complete spending conditions. Verification is strictly easier than computation (Post's Theorem), so we can actually verify a Turing-complete language with a Turing-*in*complete language! This is Simplicity.

We want a structured language like Miniscript because it comes with lots of benefits: We can check that programs are correct, we can compose two programs into a larger one, we can analyze programs, and overall programs are machine-readable.

Lastly we want formal program semantics to be able to write a formal specification about what a program does and to be able to prove that a program satisfies its specification.

## What Simplicity Is

Simplicity can be thought of as an extension of Miniscript.

It is a functional language where programs are nested functions, which we call _combinators_. There are nine combinators (unit, iden, take, drop, injl, injr, pair, comp, case) plus some more specialized ones (witness, assertl, assertr, fail, jets).

As you can see, the instruction set is small, like in RISC. The instructions are also very low-level like in assembly. This is a difference to Miniscript which has high-level fragments like public keys.

The semantics of a Simplicity program are defined for the Coq theorem prover.

## More Links

[If you know Rust, you know Simplicity.](https://github.com/uncomputable/simple-playground)

[Verifying the Computation of a Turing Machine in Simplicity](https://github.com/uncomputable/simple-turing)

[Creating Simplicity Transactions For Elements Core](https://github.com/uncomputable/tappy/tree/simplicity)

[Visualizing Simplicity Programs](https://github.com/uncomputable/simple-companion)
