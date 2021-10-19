# Cosmos-Hub Vega Upgrade Public Testnet Instructions

We are running a public testnet for the Vega upgrade. All Cosmos Hub validators are invited to participate in the public testnet. In addition, we are providing a few public endpoints for testing integrations.

We are also available on the `#validators-verified` channel in the [Cosmos Developers discord](https://discord.gg/cosmosnetwork) for support.

## Joining as a validator
You can continue using the same account and validator key as the one you're using for `cosmoshub-4`. If you'd like to request testnet ATOMs for delegation, please make an issue with your delegator account information.

## Schedule 🗓️ 

⚠️ These dates are subject to change. Please continue checking this page for up to date timelines. ⚠️

| Date                       | Testnet plan                |
| -------------------------- | --------------------------- |
| Thursday, October 20 2021  | Launch testnet chain with Gaia v5 |
| Wednesday, October 21 2021 | Submit software upgrade proposal            |
| Thursday, October 22 2021  | Voting ends                 |
| Friday, October 23 2021    | Vega upgrade is live on the testnet |

## Configuring your full node 🎛️

### Public testnet Chain-ID

`vega-testnet`

### Genesis file

We're using a modified exported genesis file from `cosmoshub-4` where we take control over the Coinbase custody, Binance, and Certus One validator accounts to be able to continue producing blocks. You can either modify your own genesis file using the [replace_ref.sh](replace_ref.sh) script or you can download our prepared genesis file from [here](modified_genesis_public_testnet/genesis.json.gz.)

The `sha256sum` for the modified genesis file is `TODO`.

### Peers and endpoints

| Node              | Node ID                                    | Public IP      | Ports                                                 |
| ----------------- | ------------------------------------------ | -------------- | ----------------------------------------------------- |
| HYPHA "Coinbase"    | `99b04a4efd48846f654da25532c85bd1fa6a6a39` | `198.50.215.1` | p2p: `46656`, rpc: `46657`, api: `4317`, grpc: `4090` |
| HYPHA "Certus-one"  | `1edc806e29bfb380dc0298ce4fded8e3e8554e2a` | `198.50.215.1` | p2p: `36656`, rpc: `36657`, api: `3327`, grpc: `3080` |
| Interchain "Binance" Sentry | `TODO` | `TODO` | p2p: `26656 `, rpc: `26657 ` , api: `1317 `, grpc: `9090` |

#### Minimum gas
Please use `minimum-gas-prices = 0.001uatom` in your `config.toml`

## Doing the upgrade 

To use Cosmovisor to manage your upgrade, please follow the [Cosmovisor instructions in the README for the local testnet](../local-testnet/README.md#Cosmovisor).
