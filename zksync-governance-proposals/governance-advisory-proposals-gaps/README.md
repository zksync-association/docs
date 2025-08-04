# Governance Advisory Proposals (GAPs)

### What is a Governance Advisory Proposal (GAP)?

Governance Advisory Proposals (GAPs) include all proposals submitted through the ZKsync [GovOps Governor](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkGovOpsGovernor.sol). These proposals are not connected to the ZK token or to the ZKsync protocol. Instead, GovOps Governors provide legitimacy to offchain decisions through onchain Token Assembly Delegate voting.

### Types of Governance Advisory Proposals

Governance Advisory Proposals can be used for a variety of use-cases:

1. **Ratification:** Create a GAP to ratify changes to canonical governance-related documents, such as the ZKsync Governance Procedures or the ZK Credo.
2. **Elections or Nomination:** Create a GAP to elect or nominate supervisors, directors, and/or officers for specific governance bodies, in accordance with their bylaws. For example, this can include an Emergency Supervisor to the Security Council or Guardians.
3. **Governance Oracle:** Connect an external application or interoperable chain to ZKsync governance. For example, an application or a ZKsync Chain built on ZKsync Era may submit a proposal to change a specific parameter.

### What information should I include in a GAP?

A Governance Advisory Proposal should include all the necessary information for ZKsync Delegates to make an informed decision and vote on the proposal. The proposal length and detail should align with the impact of the GAP.

**All GAPs should include:**

* IMPACT: Describe how the token program will _**impact**_ assets, builders, and the community of ZKsync, and what future vision these changes will contribute to. For example, it could be focused on increasing the diversity of assets and number of builders on ZKsync, contributing to ZKsync's vibrant economy. Read more [here](https://docs.zknation.io/zk-nation/zksync-governance-system-north-star).
* RECOMMENDED ACTIONS: Describe the set of actions that the proposal is recommending. If the proposal includes changes to specific documents, specify the original document source and track changes. If the proposal advises on an election, specify the terms, responsibilities, and any relevant legal contracts.
* PLAN: Outline the relevant _**plans**_ for implementation if the proposal passes. This could include specific _**outcomes, milestones,**_ and _**deliverables.**_
* ACCOUNTABILITY FRAMEWORK: Specify what methods will hold the program, operations, and participants accountable for their commitments. For example, this can include items such as an Accountability Council, Token Streaming Terms, KYC or reputation staking.

> ✍️ TEMPLATE: Proposers are encouraged to follow the standard proposal template for Governance Advisory Proposals, available [here](https://github.com/zksync-association/governance-resources/blob/main/proposal-templates/03_gap_template_govops_governor.md).

> &#x20;ℹ️ _NOTE: All documentation should be included in the onchain proposal, or include links to an onchain source such as Arweave, IPFS, etc. This allows the proposal content to be public and accessible across web3 applications._

### What onchain actions can I execute through a GAP?

The GovOps Governor and its timelock contract, through which Governance Advisory Proposals are submitted, are not connected to the ZKsync Protocol, the ZK Token contract or other ZKsync contracts at inception. However, proposers can still include onchain actions for Governance Advisory Proposals such as:

#### Example: Adopt SEAL Safe Harbor Agreement and enshrine agreement onchain

[GAP-2](https://vote.zknation.io/dao/proposal/35395412545014978447594654620386134175315194219985614464693911512436668500487?govId=eip155:324:0x496869a7575A1f907D1C5B1eca28e4e9E382afAb) adopted the SEAL Whitehat Safe Harbor Agreement and established a rapid response mechanism that enables whitehats to effectively intervene during active exploits, safeguarding user funds and reinforcing ZKsync's proactive security measures. The agreement was registered on ZKsync Era in the Safe Harbor Registry at address 0x5f5eEc1a37F42883Df9DacdAb11985467F813877, including all adoptionDetails, ensuring transparency and immutability.&#x20;
