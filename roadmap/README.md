# EF JavaScript Team Roadmap

On this page you can find our team roadmap as well as recaps for the previous years. Roadmap updates are done throughout 
the year and try to reflect our current state of planning and thinking ahead.

Roadmaps by year:

- [2021](./EF2021.md)
- [2022](./EF2022.md)
- [2023](./EF2023.md)
- [2024](./EF2024.md)
- [2025](./EF2025.md) [ DRAFT ]

## 2024 Recap

In 2024 priorities shifted substantially over the year and some focus areas haven been downgraded substantially while others have been
newly taken in. The following sections give a quick overview on the dynamics.

### Classic EthereumJS Client Development (Downgraded)

The EthereumJS [client](https://github.com/ethereumjs/ethereumjs-monorepo/tree/master/packages/client) is an indispensable research
tool for EIP prototyping due to its highly modular structure. At the same time limits on classic usage became even more clear throughout
the year, partly by the rise of (even) more performant L1 client alternatives like the Reth Rust-based client. We have therefore substantially downgraded
implementation efforts on things like SNAP sync, a flat database layout for (stateful) state storage, a wider devp2p refactor or client 
multithreading support, which initially had some stronger presence in our 2024 roadmap. Some of these might still be useful and followed
upon on the sideline, though with less ressources applied.

### Browser Support (Substantially Upgraded)

JavaScript is THE programming language for the browser. Throughout the year it became clear that we had largely underappreciated one
central browser-related topic and challenge around our libraries: the size of the bundles created from our libraries to be possible
to be loaded in a web context. Especially for our EVM the bundles libraries (so: also including the 3rd-party dependencies) were several
100KBs too large to get efficiently loaded within a website context. We have therefore significantly ramped up efforts here, restructured
a lot of code to allow for removal of unnecessary code paths ("tree shaking") and removed unnecessary dependencies,
culminating in our October/November 2024 breaking releases with bundle size reductions e.g. for our EVM of 60% and greater.

Together with some other browser-related improvements these releases mark the first moment in time where the Ethereum L1 protocol
stack is now fully ready to be used within web browsers without substantial limitations.

### Security (Substantially Upgraded)

This topic aligns very well with the above browser support one: since the libraries are now fully browser ready (and things like
EIP-7702 account abstraction is on the horizon) they - and particularly the EthereumJS EVM - will likely be used for more
"serious" and security-sensitive production use cases in the future. To take this into account we gave security a lot stronger
emphasis than initially planned. The dependency reduction from above is also a big step towards a more secure JavaScript EVM.
Through a collaboration with Paul Millr from [noble Crypto](https://paulmillr.com/noble/) we were able to replace remaining WASM
implementations for EVM precompiles (BLS, BN254 (aka alt_BN128)) as well as the 4844-related KZG crypto with pure JavaScript
implementations (the WASM code is not auditable and therfore less secure and even excluded to be used by policy by 
security-sensitive products like MetaMask).

This makes up for a fully auditable JavaScript EVM for the first time and we plan to have an EVM audit done throughout 2025.

### EIP Implementation & Testing (Expanded)

The EthereumJS stack is historically being build up in a very modular way and is therefore well suited for EIP prototyping and
early on integration. 2024 was a year with a lot of protocol work to be done and our team increased its engagement here.

Some examples are:

- Pectra HF [devnet-3](https://notes.ethereum.org/@ethpandaops/pectra-devnet-3), prototyping (EIP-2935), lot of spec refinement work
- devnet-4, previous EIP-7702 [test filling](https://github.com/ethereumjs/ethereumjs-monorepo/pull/3737)
- Verkle [devnets](https://github.com/ethpandaops/verkle-devnets) participation, stateless block execution, spec work
- EIP-6493 Stable Container [Prototyping](https://github.com/ethereumjs/ethereumjs-monorepo/pull/3452)

Since autumn 2024 we are able to [fill execution-spec-tests](https://github.com/ethereum/execution-spec-tests/pull/752), which
is the new test format for the Ethereum L1 protocol. We plan to build upon this new capability, which aligns well with our
early-on EIP prototyping work and embed within the team in a way that we can regularly contribute new test cases throughout
2025 and therefore do a substantial contribution to secure the protocol.

### Ultralight / Portal Network

For [Ultralight](https://github.com/ethereumjs/ultralight) respectively the Portal Network, 2024 was the year where all the pieces
slowly came together. Existing specs like for the Portal history network were finalized and battle tested so that these
parts can be leveraged for concrete integration projects like making EIP-4444 (prune historical block data) a reality.

Since we have both an L1 as well as a Portal stack our team is well positioned to contribute with early prototyping, spec work and integration.

In 2024 we e.g. have [started](https://github.com/ethereumjs/ethereumjs-monorepo/pull/3196) a prototype EIP-4844 integration,
have done a lot of bootnode work to support the evolving Portal Network testnets and have substantially contributed to both
spec definition and refinement of the state network by doing a first full implementation of the spec - see e.g. PRs [#539](https://github.com/ethereumjs/ultralight/pull/539) and [#649](https://github.com/ethereumjs/ultralight/pull/649). The state network is one of the core
networks of the Portal Network data network suite with the goal to provide distributed and lightweight access to the Ethereum
state, one of the harder problems to solve due to the (growing) size of the Ethereum network state.

### Ethers.js

Ethers.js is not part of the EF JavaScript team anymore but is now an independent entity within the EF.

## Q4 2023 Recap

### DevEx & VM

- [x] Breaking Monorepo Releases Community Support

### Hardforks & EIPs

- [x] Post-Shanghai EIP implementation Work

### Research, Client & Testnets

- [x] EthereumJS Client Lightclient Strategy and Production Roadmap (somewhat, lightclient paths more clear now, but still evolving)

### Portal Network

- Launch portalnetwork v1.0.0 with history/light client update/state network functionality
- Improve Ultralight documentation and quickstart guide.
- Maintain Ultralight public bootnodes and bridge nodes.
- Update and improve Ultralight browser tools, demos, and documentation.
- History Network Reference Production Integration Partnership (based on Q3 analysis)

### Ethers.js

- This will be (likely) almost entirely focused on v7 features, refactoring and 
- Migrating v6 ancillary packages to be v7-ready with collaborator assistance
- Updating documentation for v7

## Q3 2023 Recap

### DevEx & VM

- [x] Final Breaking Monorepo Releases

### Hardforks & EIPs

- [x] EIP-4844 Robustness Work & Live Testing
- [x] ~~EOF EIPs Robustness Work & Live Testing~~ (EOF stuff postponed, roadmap changes)

### Research, Client & Testnets

- [x] ~~Post-Shanghai Functional EIP/HF Testnet~~ (no, turned out EIP-4844 taking a lot more space than expected)
- [x] EthereumJS Client Portal Network Integration Feasibility Analysis (somewhat: Lodestar/Ultralight integration)
- [x] EthereumJS Client LES sync via engine API (Beacon Light Client) (somewhat: Lodestar/Ultralight integration -> CLient integration with Lodestar/Ultralight)

### Portal Network

- [x] Deep testing and debugging of client interop in Portal-Hive
- [x] Implement initial spec for Beacon Light Client Network
- [x] Experimental integration of Portal and LightClient
- [x] Convert Ultralight testing suite to vitest
- History Network Reference Production Integration (e.g. EthOS, other) Analysis

### Ethers.js

- Ancillary libraries for Contract Wallets; a small (but vocal) group has been advocating for this, so it may be moved earlier; the goal is to get a working demo and then allow them to further contribute
- More serious planning for v7, as I want to switch to a more regular annual release cycle to reduce the impact on version bumps by making more, smaller major releases
- Expand the cookbook section with more real-world examples, with JS and Solidity; EIP-712, signing, tokens, etc.

## Q2 2023 Recap

### DevEx & VM

- [x] ~~VM/EVM Optimism L2 Support Integration (depends on Q1 analysis)~~ postponed, but some base work done in PR [#2713](https://github.com/ethereumjs/ethereumjs-monorepo/pull/2713)
- [x] Monorepo-wide Node.js Buffer -> Uint8Array Switch (huge, but: Browser + React Compatibility!) 🎉
- [x] Transaction Library Refactor (Modularize -> Typed Tx Diversification!) (later: Q3 2023)
- [x] Monorepo-wide ESM Build Support (along Summer 2023 breaking releases)
- [x] Breaking Monorepo Releases v7 (Beta)

### Hardforks & EIPs

- [x] EIP-4844 Shard Blob Transactions Spec Finalization (later, spec not finalized at that point)
- [x] ~~EOF Implementation: EIP-4200 Static Relative Jumps~~ (EOF stuff postponed, roadmap changes)
- [x] ~~EOF Implementation: EIP-4750 EOF Functions~~ (EOF stuff postponed, roadmap changes)
- [x] Shanghai HF Preparations (Testnets, Developer Tools, Community Support)

### Research, Client & Testnets

- [x] EIP-4844 Shard Blob Transactions Multi-Client Testnet
- [x] ~~Multi-client EOF-focused testnet~~ (EOF stuff postponed, roadmap changes)
- [x] Verkle Tree Specification Updates
- [x] ~~EthereumJS Client SNAP Sync Production Release~~ (no, takes longer than expected)
- [x] Client In-browser sync feasibility analysis (Lodestar Light Client + Sepolia LES)

### Portal Network

- Explore integration of Lodestar or Kevlar CL light client with Ultralight for feeding light client update data to Beacon Light Client Update Network
- [x] Build WebRTC transport layer for discv5 to allow direct p2p connections for browser clients
- [x] R&D of solutions to challenges in Merkle basic State Network design and client implementation
- Begin implementation of Rendezvous protocol in Discv5

### Ethers.js

- Release tools.ethers.org, a tool to simplify many common debugging tasks as well as quickly testing open issues marked “investigate” (currently playground.ethers.org handles much of this, but tools is for more specific issues)
- Begin opening up additional repositories, adding other external contributors to help with Network-specific v6 plugins and ancillary libraries like LedgerSigner
- Migrate many “common” issues/discussions to the documentation cookbook section and Ethereum basics section and add links to the issues/discussions to these sections of the documentation

## Q1 2023 Recap

### DevEx & VM

- [x] VM/EVM Performance Improvements (Memory Management, Others)
- [x] VM/EVM (Other) Post-Breaking Release API Optimizations
- [x] VM/EVM Optimism L2 Support Feasibility Analysis (partly, see PR [#2713](https://github.com/ethereumjs/ethereumjs-monorepo/pull/2713) and related)
- [x] EVM Standalong Capabilities (after VM/EVM extraction) (done a bit later along Summer 2023 breaking releases)

### Hardforks & EIPs

- [x] EIP-4844 Shard Blob Transactions Draft & Local Geth Testnet Integration
- [x] EIP-4844 Shard Blob Transactions KZG Library Analysis & Integration
- [x] EIP-4895 Beacon Chain Withdrawals (Shanghai) Spec Finalization

### Research, Client & Testnets

- [x] Integration of the EthereumJS Client with Verkle Testnets (Condrieu, Beverly Hills, and Future Ones)
- [x] Verkle Trie "Stateless" State Management and Proof Verification
- [x] Verkle Tree Specification Work & Performance Analysis
- [x] EthereumJS Client SNAP Sync Draft Implementation (yes, but later)
- [x] ~Reactivate Client Browser Build~ -> Stalled until active use case (statelessness)

### Portal Network

- Wrap up any loose ends from History Network implementation - (alpha version of portalnetwork module for chain history)
- Implement prototype of Beacon light client update network
- [x] Begin exploration of WebRTC to allow for p2p discovery of browser clients using libp2p/waku gossip

### Ethers.js

- Documentation-specific pull request templates, GitHub actions and webforms to streamline (while retaining safety) user-contributed documentation changes to code
- Much richer stats and tools to drill down into build.ethers.org for tracking changes, code coverage and testing (especially for auditing purposes)
- More documentation, especially regarding Ethereum basics, based on common issues; this will be open to additional contributors too
- Aggressive resolving and closing of GitHub issues and PRs; hopefully v6 will have resolved many of these, others can be migrated to discussions
- Migrating to (or at least making a stronger presence) Mastodon for ethers for its advisories


## Q4 2022 Recap

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

## Q3 2022 Recap

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

## Q2 2022 Recap

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

## Q1 2022 Recap

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


## Q4 2021 Recap

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

## Q3 2021 Recap

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

## Q2 2021 Recap

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

## Q1 2021 Recap

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

