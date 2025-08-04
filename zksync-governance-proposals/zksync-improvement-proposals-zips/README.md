# ZKsync Improvement Proposals (ZIPs)

### What is a ZKsync Improvement Proposal (ZIP)?

ZKsync Improvement Proposals (ZIPs) include all proposals submitted through the ZKsync [Protocol Governor](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkProtocolGovernor.sol). The Protocol Governor is a smart contract deployed on ZKsync Chain Era, and ZIPs are used to propose upgrades to the ZKsync protocol. Protocol Governor proposals are executed through the transmission of a message from ZKsync to Ethereum.

### Types of Protocol Upgrades

The Protocol Governor is responsible for executing proposals related to:

* Upgrades to the ZKsync protocol
* Upgrades to the Protocol Governor, Token Governor, and GovOps Governor
* Upgrades to the ZK token contract
* Upgrades to the Security Council Multisig (i.e. to the Security Council and Security Council members)
* Upgrades to the Guardian Multisig (i.e. to the Guardians and Guardian members)
* ZKsync Layer 2 Era upgrades

### What information should I include in a ZIP?

A ZKsync Improvement Proposal should include all the necessary information for ZKsync Delegates to make an informed decision and vote on the proposal. The proposal length and detail should align with the impact of the ZIP.

**All ZIPs should include:**

* MOTIVATION: Detail why this ZIP is necessary and what issues or opportunities it seeks to address within the ZKsync ecosystem. Discuss the benefits of the proposed changes to users and developers. Read more [here](https://docs.zknation.io/zk-nation/zksync-governance-system-north-star).
* SPECIFICATION: The technical specification should describe the syntax, semantics, and any new components. This section should be precise enough to enable developers to implement the change.
* RATIONALE: Discuss the rationale behind the design decisions and the approach taken. Explain why key choices were made and describe alternative solutions that were considered, if appropriate.
* BACKWARDS COMPATIBILITY: Discuss any backward compatibility issues. Describe the impact of the proposed change on existing applications, contracts, or the broader ZKsync protocol, highlighting how backward compatibility is handled or why breaking changes are necessary.
* SECURITY CONSIDERATIONS: Examine the security aspects related to the proposal. Discuss potential threats, risks, and vulnerabilities, and explain how they are addressed or mitigated.

> ✍️ TEMPLATE: Proposers are encouraged to follow the standard proposal template for ZKsync Improvement Proposals, available [here](https://github.com/zksync-association/governance-resources/blob/main/proposal-templates/01_zip_template_protocol_governor.md).

_NOTE: We recommend all documentation is included in the onchain proposal, or linked with an onchain source such as Arweave, IPFS, etc. This allows the proposal content to be public and accessible across web3 applications._
