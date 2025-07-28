# ZIP FAQ

> Find full technical documentation for the ZKsync protocol at [zksync.io](http://zksync.io).

### How can a ZIP upgrade the ZKsync Protocol?

The Protocol Governor contracts (L2) have a direct link to “protocol upgrade handler” for the ZKsync protocol that is deployed on L1. The ZIP improvement proposals (ZIPs) give instructions to the protocol upgrade handler on L1, and the upgrade handler executes changes on L1 & L2 contracts.

### What is included in the “core” ZKsync protocol?

* [L1 contracts](https://docs.zksync.io/zksync-protocol/contracts/l1-contracts): a set of contracts that powers interaction with the rollup on Ethereum. (e.g. Verifier Contract)
* [System contracts](https://docs.zksync.io/zksync-protocol/contracts/system-contracts): a set of contracts deployed on L2 that are responsible for various protocol functions. (e.g. L1 Messenger, Default Account Contract, Storage Management Contract)
* [Bootloader](https://docs.zksync.io/zksync-protocol/contracts/bootloader): Part of the execution environment in which all the transactions are executed on L2.
* Proof System
  * ZK circuits: ZK circuits generate cryptographic proofs (e.g., zk-SNARKs or zk-STARKs) that attest to the validity of batched state transitions on L2. These ensure that all operations on L2 are valid without needing to replicate the computational workload on L1. Read more [here](https://docs.zksync.io/zksync-protocol/circuits).

### What is the upgrade handler?

The [upgrade handler](https://etherscan.io/address/0xE30Dca3047B37dc7d88849dE4A4Dc07937ad5Ab3) is the owner of State Transition Managers & owner of L1 shared bridge, bridge hub & other contracts (e.g USDC bridge or L2 bridge counterparts).

### What is the Change Type Manager?

A [Change Type Manager (CTM)](https://docs.zksync.io/zksync-protocol/contracts/l1-contracts/l1-ecosystem-contracts#state-transition-manager-stm) is a critical component designed to handle and coordinate the execution of operations that span between Layer 1 (L1) and Layer 2 (L2). It serves as a factory to deploy ZKsync Chains, and it is responsible for ensuring that all the ZKsync Chains deployed by it are up-to-date. It ensures that all state transitions comply with the ZKsync protocol's rules and guarantees data consistency, and ensures consistency, validity, and synchronization across these layers.

All current ZKsync Chains are deployed to the main ZKsync CTM. However, this may change if/when the Gateway upgrade is executed.

### What are the different types of state changes that a ZIP can include?

* Type 1: Protocol upgrade that _does not_ affect ZKsync Chains
  * Example: Changes to Governor parameters (e.g. change voting delay from 7 days to 3 days)
* Type 2: Protocol upgrade that _does_ affect ZKsync Chains, but _does not_ require action
  * Example: Upgrading bridge functionality, Upgrading bridge functionality, adding new State Transition Managers, Adding a new ZKsync Chain with a custom state (e.g. [ZIP-7 Lens Chain inclusion on Elastic Network](https://vote.zknation.io/dao/proposal/53064417471903525695516096129021600825622830249245179379231067906906888383956?govId=eip155:324:0x76705327e682F2d96943280D99464Ab61219e34f))
* Type 3: Protocol upgrade that _does_ affect ZKsync Chains _AND_ requires an action from ZKsync Chains
  * Example: Any protocol version change (e.g. [ZIP-3 Protocol Defense](https://vote.zknation.io/dao/proposal/39897055470405054808751466940888279812739313934036970931300785151980460250983?govId=eip155:324:0x76705327e682F2d96943280D99464Ab61219e34f))

### For ZIPs that do require action from ZK Chains, what does that look like?

**Standard Case:** If a state-change protocol upgrade to the ZKsync protocol is successfully approved via a ZIP, each individual ZKsync Chain admin will have to upgrade to the new version by set deadline, otherwise a chain that doesn’t upgrade will not be able to commit new batches. A few examples:

* Circuit upgrade: If there is an upgrade of ZK circuits from 1.0 to 2.0, you are changing what is enshrined in L1 but also updating all parameters of ZKsync chains to adopt new proof generation process.
* Interop: When interop arrives and if it the upgrade passed through governance, all chains will have Interop: Interop will be introduced in the v29 protocol upgrade. If approved by the Token Assembly, ZKsync Chains who want to access interop will have to be on v29 to use it. However with later upgrades, ZKsync Chains who remain on v29 will still be able to send interop to v30+ Chains.

**Defensive Case (governance force upgrade)**: In the case of an emergency, a protocol upgrade approved by governance may force an upgrade to a specific chain or all Chains.

* Example: Emergency upgrade needed to fix circuit bug that allows bad batch to be proven even if it is not proven.

### Can ZKsync Chains opt out of an upgrade that is approved by the passing of a ZIP?

It is possible to run an outdated version as long as it has not been disabled, but it is not recommended to be more than 1 version behind the latest version.

The dev team who proposes the ZIP should always provide clear deadlines as to when ZKsync Chains should upgrade to the latest version.

### What are the exact list of params that the ZKsync Chain admin have control over? Can these be impacted by ZIPs?

Every ZKsync Chain has an admin contract known as the ChainAdmin.

The roles each ChainAdmin of a ZKsync Chain has can be [found here](https://docs.zksync.io/zk-stack/running/ownership-model#roles-overview)

> ℹ️ ZIPs currently cannot impact these parameters.
