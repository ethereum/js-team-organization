# EF JavaScript Team Roadmap

On this page you can find our team roadmap.

Roadmap updates are done throughout the year and try to reflect our current state of planning and thinking ahead.

This "live" roadmap document is based on the yearly roadmap submission we have done within the EF, see the following
list for an overview of the initial roadmaps from the respective years.

- [2021](./EF2021.md)
- [2022](./EF2022.md)
- [2023](./EF2023.md)

## Q4 2022 (incomplete)

### DevEx & VM

- [x] Dedicated RPC-backed EthersStateManager for easier Mainnet Transaction Debugging

### Hardforks & EIPs

- [x] EIP-4895 Beacon Chain Withdrawals Support (Shanghai HF)
- [x] EIP-3540 / EIP-3670 EVM Object Format (EOF) Test/Specification Work

### Research, Client & Testnets

- [x] Early Pre-Shanghai EthereumJS/Lodestar-based Shandong Testnet (https://shandong.ethdevops.io/) 🎉
- [x] Client UX-focused RPC Improvements (eth_gasPrice, eth_feeHistory,...)
- [x] Lodestar/EthereumJS CL/EL Client Combination Live Testing and Optimization
- [x] Structural Dynamic Testnet Setup Automation / Post-Merge Testnet Improvements
- [x] Verkle Trie "Stateless" State Management and Verkle Blocks Processing

### Portal Network

- [x] History Network Protocol Spec Update (Accumulator/ChainID/Content-Key changes)
- [x] Continued Browser Client UX Improvments
- [x] Database Pruning for Subprotocols
- [x] UTP Protocol Congestion Control Refactor

### Ethers.js

- [x] Ethers v6 Release Candidate
- [x] Ethers v6 Release Documentation Updates

## Q3 2022

### DevEx & VM

- [x] VM/Monorepo Breaking Release Finalization Work (Community Feedback)
- [x] Default Merge HF for all Monorepo Libraries
- [x] Trie Library Generalization/Modularization (DB / Hash Function)
- [x] UX focused Trie Library Refactor (Renamings / Customizability)
- [x] Monorepo Package NPM Dependency Reduction Part I (security)
- [x] Monorepo Adopt Stricter Code Formatting Rules (Linting) (security)
- [x] GitPOAP Cooporation EthereumJS Monorepo
- [x] Monorepo Geth Genesis Format Compatibility (VM/Tx/Block/Client)
- [x] Monorepo Final Breaking Releases 🎉

### Hardforks & EIPs

- [x] Merge HF Spec Finalization
- [x] Sepolia Merge HF Integration
- [x] Merge HF Community Integration Support (Hardhat, Ganache, Other)

### Research & Client

- [x] SNAP Protocol Base Layer Implementation (Networking/devp2p)
- [x] Client SNAP Protocol Synchronizer Draft

### Portal Network

- [x] Deeper Header Accumulator Integration (History -> getBlockByNumber, Header Proof Validation)
- [x] Refactored RPC Method Exposure Base Layer
- [x] First Draft of `portalnetwork` `ethers` compatible `JsonRpcProvider` integration 🎉
- [x] Improved Portal Network Experimentation Console (Browser Client)
- [x] History Network Receipt Integration

### Ethers.js

- [x] Integrated new ENS normalization specification
- [x] EIP-712 Type Exports
- [x] Continued Improved L2 Integration (Arbitrum/Optimism)

## Q2 2022

### DevEx & VM

- [x] VM Improved L2 Modularization (custom Precompiles, separated VM/EVM)
- [x] Expanded Chain Customizability (L2/Others) (extracted StateManager, encapsulated Blockchain consensus)
- [x] Selected VM Performance Optimizations (not as far reaching as planned)
- [x] Wide-reaching Code Clean-Up Work and Deprecations on various Libraries (Breaking Release Preparation)
- [x] VM Native JavaScript BigInt Integration (performance / security)
- [x] Crypto Primitives (Hash, Signature) Library Switch to modern audited Library (Noble) (security)
- [x] Trie Library Database Abstraction
- [x] Monorepo Package Unification (consistent @ethereumjs namespace)
- [x] Monorepo Breaking Releases (Beta 1)

### Hardforks & EIPs

- [x] Merge HF Spec Update Implementation (Engine API / Beacon Sync)
- [x] EIP-5133 GrayGlacier HF Support (Difficulty Bomb, Merge Preparation)
- [x] EIP-3074 Authcall Implementation 

### Research & Client

- [x] Client "Grown-Up" Transaction Pool Integration
- [x] Both lightweight sync + verkle tree implementation postponed (breaking release focus)

### Portal Network

- [x] Initial Android App (Portal Network PoC for Mobile Context)
- [x] Header Gossip Subnetwork Integration 
- [x] Stable communication with other clients (Fluffy/Trin) for sub networks from Q1
- [x] Rendevous Protocol Integration (ENR request along NAT/Firewall issues)
- [x] External ChainSafe DiscV5 library integration
- [x] Browser-Support Analysis and PoC (Web-Storage)
- [x] Specification Implementation Refactoring (dedicated Protocol class)
- [x] Header Accumulator Spec Implementation (History Network)
- [x] First Canonical Indices Protocol version
- [x] Ultralight Electron App
- [x] `portalnetwork` library API PoC (`getBlockByNumber` RPC Call)

### Ethers.js

- [x] Focus on tooling, especially on the playground and the toolkit
- [x] Improved L2 Integration (Optimism/Matic)

## Q1 2022

### DevEx & VM

- [x] VM Support Feasibility Analysis for EVM equivalent L2 Solutions (e.g. Optimism)
- [x] VM Modularization (Custom Opcodes, Precompiles, State) (L2 Support)
- [x] 1 additional VM/client hire (Gajinder Singh)
- [x] Breaking Release Preparation (Summer 2022): BigInt Refactor
- [x] Breaking Release Preparation (Summer 2022): Noble Crypto Library Integration
- [x] Breaking Release Preparation (Summer 2022): StateManager extraction

### Hardforks & EIPs

- [x] Production-ready Merge releases of VM and other libraries (Kiln v2.1 specs)
- [x] First Shanghai HF EIP implementations (scope still open)
- [x] EIP-3855: PUSH0 instruction (Shanghai CFI)
- [x] EIP-3860: Limit and meter initcode (Shanghai CFI)
- [x] EIP-1153: Transient Storage Opcodes
- [x] EIP-3540: EVM Object Format (EOF) v1 (Shanghai CFI)
- [x] EIP-3670: Code Validation (Shanghai CFI)

### Research & Client

- [x] Client Mainnet Sync Improvements (more robust Fetcher logic)
- [x] Merge Kiln testnet support
- [x] First EthereumJS (+ Lodestar) block proposal on public testnet (Kiln)
- [x] Light Client Work (PoC) with Lodestar (VM/Trie Proof functionality), e.g. [here](https://github.com/ChainSafe/eth2-light-client-demo/pull/28)
- [x] Hive (https://github.com/ethereum/hive) Test Framework Integration 
- [x] Verkle Demo Network PoC (Stateless block execution EthereumJS Client) (Project with Geth, Guillaume Ballet, others)

### Portal Network

- [x] Structural Setup (Monorepo, Software Tests, CI, Code Cleanup)
- [x] Robustness of the networking layer (`portalnetwork` module)
- [x] Draft implementation for 1-2 sub networks (e.g. state / history)
- [x] Stable browser networking topology
- [x] Integration in semi-public test network with other clients (Fluffy, Trin)
- [x] Portalnetwork block explorer PoC
- [x] Demo integrations with Android and iOS
- [x] 1-2 additional hires for the project

### Ethers.js

- [x] Ethers v6 release preparation (release planned April/May 2022)
- [x] EIP-2098 compact signatures 
- [x] EIP-2544 ENS Wildcard support
- [x] Better IPFS support


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

