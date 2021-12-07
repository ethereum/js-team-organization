# EF JavaScript Team Roadmap

On this page you can find our team roadmap.

Roadmap updates are done throughout the year and try to reflect our current state of planning and thinking ahead.

This "live" roadmap document is based on the yearly roadmap submission we have done within the EF, see the following
list for an overview of the initial roadmaps from the respective years.

- [2021](./EF2021.md)
- [2022](./EF2022.md)

This planning is based on the following theoretical assumptions on an outer timeline (note that there is no evidence or public statements that these dates will happen to any extend):

- "The Merge" happening in spring 2022
- Shanghai HF happening around summer 2022
- Stateless happening somewhat after "The Merge"

## Q4 2021

General Library Work:

- [x] EthereumJS: continued hardening (bug resilience, performance) of VM by client, mainnet progress, [Shanghai Attack Work](https://github.com/ethereumjs/ethereumjs-monorepo/issues/1536)
- [x] EthereumJS: continued performance work (VM, other), e.g. [VM](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1570), [Tx](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1532)
- [x] EthereumJS: Client Reliability and Sync Improvements, e.g. [here](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1543)

Hardforks / Releases:

- [x] EthereumJS -> Non-Breaking Releases: VM dynamic gas cost [refactor](https://github.com/ethereumjs/ethereumjs-monorepo/issues/1169) (better Hardhat gas cost reporting), StateManager [refactor](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1548), [non-HF EIPs](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1568) (EIP-3607, EIP-2681)
- [x] EthereumJS ArrowGlacier HF [Releases](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1555)
- [x] EthereumJS Better Optimism L2 Support

Dedicated Projects:

- [x] EthereumJS: "The Merge" Pithos, Kintsugi Testnet Releases (Client, Blockchain, Block, Common)
- [x] EthereumJS: [Verkle Tree](https://notes.ethereum.org/@vbuterin/verkle_and_state_expiry_proposal) WASM compile from Rust (Geth cooperation)
- [x] EthereumJS: EthereumJS Client Verkle Proof Consumption + Stateless execution, first prototype (Geth cooperation)
- [x] EthereumJS: [Portal Network](https://github.com/ethereum/stateless-ethereum-specs/blob/master/portal-network.md) Structural Project Setup (Repositories, team planning)

Ethers:

- [ ] Ethers: ethers/v6, with an emphasis on using more moderns JavaScript features (ES5), more comprehensive TypeScript and ancillary packages (enabling easier external contributors)

## Q3 2021

General Library Work:

- [x] EthereumJS: continued performance work (VM, other), monorepo [performance-related issues](https://github.com/ethereumjs/ethereumjs-monorepo/issues?q=is%3Aopen+is%3Aissue+label%3A%22type%3A+performance%22)
- [x] EthereumJS: Stateless work with some focus on VM stateless execution and improved witness support/integration (eventually divide between Q3/Q4)
- [x] EthereumJS: Initial L2 Support (Arbitrum, Polygon, xDai), PR [#1317](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1317)
- [x] EthereumJS Client: Sync improvements / basic tx pool
- [x] EthereumJS Client: Miner / Local dev testnets

Hardforks / Releases:

- [x] EthereumJS Client: First stable v0.1 release
- [x] EthereumJS: Improved Custom Chain Support

Dedicated Projects:

- [x] EthereumJS Client: [The Merge](https://github.com/ethereum/eth2.0-specs#merge) structural integration (Client, other)
- [x] EthereumJS Client: [The Merge](https://github.com/ethereum/eth2.0-specs#merge) testnet participation (Interop event), see e.g. [Twitter](https://twitter.com/ralxzryan/status/1445046796305289221)
- [x] EthereumJS: [Portal Network](https://github.com/ethereum/stateless-ethereum-specs/blob/master/portal-network.md), early experiments and PoC implementations (handshake for a selected protocol)

Ethers:

- [x] Ethers: ethers issue and PR burn-down, closing issues and moving discussion issues to the discussions feature
- [x] Ethers: new website, adding the new tools, starting with the Playground and Toolbox (stretch goal of the Wallet w/ transaction composer)

## Q2 2021

- [x] EthereumJS VM: Block Builder API (Hardhat / Client), PR [#1158](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1158)
- [x] EthereumJS: Post-Berlin ecosystem update work, e.g. PR [1206](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1206)
- [x] EthereumJS: Tx Library ecosystem usability & documentation work, e.g. PR [#1214](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1214) or PR [#1283](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1283)
- [x] EthereumJS devp2p: Reliability improvements, first production-ready release, PR [#1218](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1218)
- [x] EthereumJS: London preparation / active London research work, e.g. PR [#1218](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1218)
- [x] EthereumJS: EIP-1559, PR [#1239](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1239)
- [x] EthereumJS: London EIPs (EIP-3529, EIP-3541), e.g. PR [#1239](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1239)
- [x] EthereumJS Client: First "The Merge" draft implementations, PR [#1265](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1265)

- [x] Ethers: [v5.4](https://github.com/ethers-io/ethers.js/blob/master/CHANGELOG.md#ethersv540-2021-06-26-0150) EIP-1559
- [x] Ethers: [v5.3](https://github.com/ethers-io/ethers.js/blob/master/CHANGELOG.md#ethersv530-2021-05-31-1841) Elliptic-related fixes
- [x] Ethers: [v5.2](https://github.com/ethers-io/ethers.js/blob/master/CHANGELOG.md#ethersv520-2021-05-17-1618) BigInt, custom Contract Errors

- [x] Team: 1 new full-time and 2 new part-time hires

## Q1 2021

- [x] EthereumJS: Clique PoA Protocol Integration, PR [#1032](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1032)
- [x] EthereumJS: Custom Chain / L2 Improvements I, PR [#1034](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1034)
- [x] EthereumJS: Berlin HF Support & EIP Implementations (e.g. EIP-2718, EIP-2930), PR [#1048](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1048) and PR [#1151](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1151)

- [x] EthereumJS VM: Ecosystem Education & Debugging Experience, PR [#1080](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1080)

- [x] EthereumJS Client: VM Execution, PR [#1028](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1028)
- [x] EthereumJS Client: Developer Testnet Readiness (Yolo v3 and beyond), PR [#1129](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1129)
- [x] EthereumJS Client Beam Sync (Head State) Draft Implementation
- [x] EthereumJS Devp2p/Client: ETH/65 Implementation, PR [#1159](https://github.com/ethereumjs/ethereumjs-monorepo/pull/1159)

- [x] Ethers: EIP-2718 & EIP-2930 Support, Release [v5.1.0](https://github.com/ethers-io/ethers.js/releases/tag/v5.1.0)
- [x] Ethers: Ecosystem coordination for EIP-2930 (Etherscan, Alchemy and Pocket)
- [x] Ethers: v6 Planning

