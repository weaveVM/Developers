## How to Deploy rollup on WVM as L1

Because WVM is share a property of EVM equivalence the asnwer is straightforward: you may deploy an op-stack rollup on WVM as on any other EVM chain e.g Ethereum Mainnet, Ethereum testnets (Sepolia and etc).

You will need to pass WVM specific params and get tWVM tokens:

chain id: 9496
block time: 1s 
execution clien RPC UR:  https://testnet-rpc.wvm.dev
consensus client RPC URL: http://34.141.88.80:5052

TO get alphanet tWVM tokens to fund ADMIN, SEQUENCER and other accounts
please use our faucet:  https://wvm.dev/faucet
also you may for them in our discord community: https://dsc.gg/wvm

you may see an example of assets which was used to run op-node, op-geth and other executables in our optimism monorepo fork: https://github.com/weaveVM/optimism/tree/deploy-op-stack-rollup-on-wvm-l1
branch: deploy-op-stack-rollup-on-wvm-l1
If you will encounter some WVM chain specific issues like unavailable or not supported RPC calls please create an issue in this repo.

In general you just need to follow the docs and tutorial from Optimism.

core tutorial: https://docs.optimism.io/builders/chain-operators/tutorials/create-l2-rollup

it's important to understand parts which you will deploy and how they released cause you will build executable from one branch and build contracts from another! For example:

tag to make binaries: [v1.9.2](https://github.com/ethereum-optimism/optimism/tree/v1.9.2)

tag to deploy contracts: https://github.com/ethereum-optimism/optimism/releases/tag/op-contracts%2Fv1.6.0

All this info may change with the op-stack so it's important to see the latest code.

Also read the docs on each of the deployment step:
- contracts deploy: https://docs.optimism.io/builders/chain-operators/deploy/smart-contracts
- genesis generation: https://docs.optimism.io/builders/node-operators/configuration/base-config#initialization-via-genesis-file
- configuring op-node: https://docs.optimism.io/builders/node-operators/configuration/base-config#configuring-op-node

it's important to read this discussion cause optimism tutorials DON'T handle the latest upgrades and the latest development progress!

optimism dev troubleshouting discussion: https://github.com/ethereum-optimism/developers/discussions/17