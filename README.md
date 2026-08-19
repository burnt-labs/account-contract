# XION Account Contract

The primary MetaAccount implementation for the XION network — the
governance-deployed smart contract at the core of XION's account abstraction.
It authenticates transactions against a set of pluggable authenticators
(Secp256K1, EthWallet, JWT, Secp256R1, passkeys, `sign_arb`) and manages
authenticator addition and removal on the account.

This repository was split out of
[`burnt-labs/contracts`](https://github.com/burnt-labs/contracts) with its
history preserved; the contract previously lived at `contracts/account`.

## Building

```sh
cargo wasm    # optimized wasm build (alias for build --release --lib --target wasm32-unknown-unknown)
cargo schema  # generate JSON schema
cargo test
```

Reproducible release artifacts are built with
[`cosmwasm/optimizer`](https://github.com/CosmWasm/optimizer):

```sh
docker run --rm -v "$(pwd)":/code cosmwasm/optimizer:0.17.0
```

## Security

This contract is an asset in the
[Core Protocol Contracts bug bounty program](https://github.com/burnt-labs/bug-bounty/blob/main/programs/contracts.md).
See [SECURITY.md](SECURITY.md) for how to report a vulnerability.

## License

[MIT](LICENSE)
