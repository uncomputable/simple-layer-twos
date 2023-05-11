# Rollups + Simplicity

## Rollups = "Trustless Sidechains"

Rollups are a L2 system. They can have utxos or accounts; it can have Bitcoin Script or the EVM; anything is possible. On L1, the rollup exists as a rollup UTXO that is a recursive covenant. All interactions with the rollup on L1 happen by spending the rollup UTXO and by creating a successor rollup UTXO, as by the covenant.

Rollups have a two-way peg: L1 users can peg in and L2 users can peg out.

Each L2 block is a L2 state transition: There is the old state before the block and the new state after. The L2 rules define if one can go from the old state to the new state. If this is the case, then one can generate a zero-knowledge proof that proves that the state transition is legal. The proof is written in a way such that it can be verified very fast and such that it is small. This validity proof is put on L1 for full nodes to verify. This means rollups are verified by L1. The entire L2 state is also put on L1 in a compressed form. This means that the latest state can be reconstructed from the genesis state.

## Upsides

Rollups allow for all kinds of features, including better scripting, financial assets, larger blocks, confidential transactions with hidden amounts and addresses, and other cryptography. Rollups are trustless, which separates them from federated sidechains. Rollups have a two-way peg, which allows users to move between systems, unlike spacechains. Also, it goes without saying, but rollups are backed by Bitcoin, so the ecosystem stays united, unlike with altcoins.

## Downsides

Zero-knowledge proofs are complex technology that has only recently seen traction. Often one has to choose between two evils: small proofs with a trusted setup (and potential toxic waste), or a transparent system (that doesn't need a trusted setup) with larger proofs than we like. Putting the L2 state and validity proof on L1 costs also in bandwidth and computation. Lastly, the rollups cannot infinitely scale: Validity proofs need to be created, which takes time (much more than verifying the proofs). Each proof has to be included in a L1 block, which have a constant rate. There are L1 bounds that limit the maximum size of the L2 state and the proof.

## Simplicity to the Rescue

Simplicity allows you to write better code, including loops, arbitrary logic and programmatic shortcuts (which we call jets). Simplicity is low-level, but because of its flexibility it allows for many possible front-ends. This will reduce development time, code complexity and the potential for error.

One of the issues of current rollup implementations is the fact that very large values need to be hashed, which is not supported by Bitcoin Script. Simplicity supports streaming hash operations which take as many bits of input as you want. Another pressure point is introspection, which is freely configurable with Simplicity.

We might also want assurance that a rollup implementation works as intended. To do this, we can write a formal specification of the ZKP implementation (a Simplicity program). _This step alone often reveals critical errors._ We can also write a formal spec of the L1 covenant and of the L2 state transition. These sit on a higher level than Simplicity (between transactions), but Simplicity encourages formal verification and makes it easier in general. At this point we haven't proven anything, but we have written down what we meant to implement, plainly and clearly. This is a huge improvement. If we want to go the extra mile, we can now prove that our implementation satisfies our spec. This is a lot of work, but Simplicity enables that, too.

## Simplicity Front-Ends

### Policy and Miniscript

[Link](https://bitcoin.sipa.be/miniscript/)

```
// Policy
and(pk(A),or(pk(B),or(9@pk(C),older(1000))))
// Miniscript
and_v(or_c(pk(B),or_c(pk(C),v:older(1000))),pk(A))
```

### Min.sc

[Link](https://min.sc/)

```
$redeem = pk(A) && sha256(H);
$refund = pk(B) && older(1000);
likely@$redeem || $refund
```

### Imperative Language?

[Link](https://www.cairo-lang.org/)

```
func array_sum(arr: felt*, size) -> felt {
    if (size == 0) {
        return 0;
    }

    let sum_of_rest = array_sum(arr=arr + 1, size=size - 1);
    return arr[0] + sum_of_rest;
}
```
