# Cosmos-Hub Vega  Upgrade Testnet Instruction

This repo provides instructions and files that help users to test vega upgrade locally or in the public testnet.
This upgrade will integrate the new release of Cosmos-SDK v0.44.2 and IBC 1.2.1 into Gaia.

## Version
- Currently: running cosmoshub-4, Gaia version: v5.0.5
- After the upgrade: cosmoshub-4, Gaia version: v6.0.0

### Local testnet
This repo provides a detailed instruction for how to conduct a local testnet, and a modified genesis file if users do not want to replace the genesis data themselves as instructed in the `local-testnet/README.md`.


### Public testnet
This repo provides a replaced genesis file which can be directly used as a genesis to run a node in testnet. This genesis file is modified from a genesis file exported from cosmoshub-4 (`original_genesis/genesis.json.gz`) by the commands in `public_testnet/replace_ref.sh`.
