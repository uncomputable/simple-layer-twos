# Fedimint + Simplicity

## Lightning Module

Alice lives in a mint and wants to pay Bob's invoice, who lives on the Lightning network. The Lightning Gateway lives in both systems. To pay Bob, Alice creates an HTLC inside the mint at a slightly higher value than Bob's invoice. The HTLC is locked by the image in Bob's invoice. The Gateways sees a potential for arbitrage. It pays Bob via Lightning, using its Lightning funds. Bob sends the preimage to the Gateway as part of the Lightning HTLC. The Gateway uses this preimage to unlock the mint HTLC. Now the Gateway has a larger number of Fedimint coins than the number of Lightning coins it had before.

## Simplicity to the Rescue

The Mint HTLC could be a Simplicity program.

Simplicity is a generic scripting language, which is more flexible and tested than the custom Rust code that is currently used in Fedimint.

Simplicity also enables many new use cases, including [PTLCs](https://bitcoinops.org/en/topics/ptlc/), [SIGHASH_ANYPREVOUT](https://bitcoinops.org/en/topics/sighash_anyprevout/) and [DLCs](https://bitcoinops.org/en/topics/discreet-log-contracts/).

## Mint Module

Simplicity programs can be put directly into ecash notes. Each note would include a cryptographic commitment to the program _(the program's Merkle root)_. When the note is spent, the associated program has to be revealed along with a witness that satisfies the program.

This would enable use cases like multisig: shared ownership of ecash.

A more complex architecture would be to put (commitments to) tap trees into ecash notes. Upon spending, one has to reveal a Merkle path to the Simplicity program, the program itself and a satisfying witness; or one provides a signature of the output key.

