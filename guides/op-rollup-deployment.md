# How to deploy an OP-Stack rollup on WeaveVM and benefit from permanent ledger archiving

## About

WeaveVM is an EVM equivalent network, meaning you can deploy OP-Stack rollups on WeaveVM just as you would on the Ethereum mainnet or testnets (Sepolia, Goerli, etc.). The key difference is that the calldata sent from your OP rollup to WeaveVM L1 is stored permanently on [Arweave OOTB](https://docs.wvm.dev/about-weavevm/weavevm-alphanet-v1), while benefiting from WeaveVM L1's high-throughput DA (~50 MBps).

## Prerequisites 

You'll need to pass WeaveVM-specific parameters and obtain tWVM tokens.

### WeaveVM Network Configuration

- Chain ID: 9496
- Block time: 1s
- Execution client RPC URL: [https://testnet-rpc.wvm.dev](https://testnet-rpc.wvm.dev)
- Consensus client RPC URL: [http://34.141.88.80:5052](http://34.141.88.80:5052)

### Get tWVM Tokens

To get alphanet tWVM tokens for funding `ADMIN`, `SEQUENCER`, and other accounts (wallets addresses): 

- WeaveVM Faucet: https://wvm.dev/faucet
- You can also request them in our Discord community:  
[https://dsc.gg/wvm](https://dsc.gg/wvm)

## Guide

You can find an example of assets used to run `op-node`, `op-geth`, and other executables in our [Optimism monorepo fork](https://github.com/weaveVM/optimism/tree/deploy-op-stack-rollup-on-wvm-l1) (Branch: `deploy-op-stack-rollup-on-wvm-l1`).

If you encounter any WeaveVM chain-specific issues, such as unavailable or unsupported RPC calls, please create an issue in this repository. In general, follow the documentation and tutorials from Optimism.

### Core Tutorial:

It's important to understand the components you're deploying and how they are released. You'll need to build executables from one branch and deploy contracts from another. For example:

- Tag to build binaries: [v1.9.2](https://github.com/ethereum-optimism/optimism/tree/v1.9.2)
- Tag to deploy contracts: [op-contracts/v1.6.0](https://github.com/ethereum-optimism/optimism/releases/tag/op-contracts%2Fv1.6.0)

This information may change as the OP Stack evolves, so always check the latest code.

[Optimism Chain Operators Tutorial - Create L2 Rollup](https://docs.optimism.io/builders/chain-operators/tutorials/create-l2-rollup)

### Additional Docs for Each Deployment Step:

- [Deploy Contracts](https://docs.optimism.io/builders/chain-operators/deploy/smart-contracts)
- [Genesis Generation](https://docs.optimism.io/builders/node-operators/configuration/base-config#initialization-via-genesis-file)
- [Configuring OP Node](https://docs.optimism.io/builders/node-operators/configuration/base-config#configuring-op-node)

It's also important to read this discussion below, as the Optimism tutorials may not cover the latest upgrades and development progress:

- [Optimism Dev Troubleshooting Discussion](https://github.com/ethereum-optimism/developers/discussions/17)
