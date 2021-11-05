# Cosmos-Hub Vega Upgrade Public Testnet Instructions

We are running a public testnet for the Vega upgrade. All Cosmos Hub validators are invited to participate in the public testnet. In addition, we are providing a few public endpoints for testing integrations.

We are also available on the `#validators-verified` channel in the [Cosmos Developers discord](https://discord.gg/cosmosnetwork) for support.

## Joining as a validator
You can continue using the same account and validator key as the one you're using for `cosmoshub-4`. If you'd like to **request testnet ATOMs from the faucet** for delegation, please make an issue with your delegator account information.

## Schedule 🗓️ 

⚠️ These dates are subject to change. Please continue checking this page for up to date timelines. ⚠️

| Date                       | Testnet plan                |
| -------------------------- | --------------------------- |
| November 5 2021  | Launch testnet chain with Gaia v5 (previous version)  |
| November 10 2021 | Submit software upgrade proposal            |
| November 11 2021  | Voting ends                 |
| November 12 2021    | Vega upgrade (Gaia v6-rc2) is live on the testnet |

## Configuring your full node 🎛️

### Public testnet Chain-ID

`vega-testnet`

### Genesis file

We're using a modified exported genesis file from `cosmoshub-4` where we take control over the Coinbase custody, Binance, and Certus One validator accounts to be able to continue producing blocks. You can either use the [replace_ref.sh](replace_ref.sh) script to modify the [genesis file here](../exported_unmodified_genesis.json.gz) or you can download our prepared, modified genesis file from [here](modified_genesis_public_testnet/genesis.json.gz)

The `sha256sum` for the modified genesis file is `89d1cb03d1dbe4eb803319f36f119651457de85246e185d6588a88e9ae83f386`.

### Peers and endpoints

| Node              | Node ID                                    | Public IP      | Ports                                                 |
| ----------------- | ------------------------------------------ | -------------- | ----------------------------------------------------- |
| HYPHA "Coinbase"    | `99b04a4efd48846f654da25532c85bd1fa6a6a39` | `198.50.215.1` | p2p: `46656`, rpc: `46657`, api: `4317`, grpc: `4090` |
| HYPHA "Certus-one"  | `1edc806e29bfb380dc0298ce4fded8e3e8554e2a` | `198.50.215.1` | p2p: `36656`, rpc: `36657`, api: `3327`, grpc: `3080` |
| Interchain "Binance" Sentry | `66a9e52e207c8257b791ff714d29100813e2fa00` | `143.244.151.9` | p2p: `26656 `, rpc: `26657 ` , api: `1317 `, grpc: `9090` |

### Minimum gas
Please use `minimum-gas-prices = 0.001uatom` in your `app.toml`

## Doing the upgrade 

To use Cosmovisor to manage your upgrade, please follow the [Cosmovisor instructions in the README for the local testnet](../local-testnet/README.md#Cosmovisor).

Make sure your machine is resourced with 16GB while performing the upgrade. The upgrade process is memory intensive.

**Note about auto-downloads:** If validators would like to enable the auto-download option (which we don't recommend), and they are currently running an application using Cosmos SDK v0.42, they will need to use Cosmovisor v0.1. Later versions of Cosmovisor do not support Cosmos SDK v0.42 or earlier if the auto-download option is enabled. Please note that with v0.1 you could face node hanging issues with your API server enabled as explained in this [issue](https://github.com/cosmos/cosmos-sdk/issues/9875). If your node is running on darwin, arm64 CPU architecture, please do not use cosmovisor auto-download because the upgrade proposal will not provide the binary download link for this architecture. Please prepare the new binary yourself from this [v6.0.0-rc2 tag](https://github.com/cosmos/gaia/tree/v6.0.0-rc2).
