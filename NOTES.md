# NOTES.md

## Versions

anchor-cli 1.1.2 · node 22.x · @codama/cli 1.6.3

## TODO 3

Required: contributor, fundraiser, mintToRaise, amount.

Resolved automatically: contributorAccount, contributorAta, vault, tokenProgram.

The `fundraiser` PDA cannot be derived in `contribute` because its seeds depend on `fundraiser.maker`, which is a field stored inside the fundraiser account itself. Since the resolver would need the account in order to derive its own address, it must be supplied by the caller. In `initialize`, the fundraiser PDA is derived from the `maker` account, which the caller already has, so it can be resolved automatically.

## Bonus

Not attempted.

## One thing that surprised me

The generated Codama client was able to automatically derive several PDAs and program accounts, making the client code much shorter than manually deriving addresses with `findProgramAddressSync`.