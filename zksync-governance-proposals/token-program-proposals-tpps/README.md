# Token Program Proposals (TPPs)

### What is a ZK Token Program Proposal (TPP)?

Token Program Proposals (TPPs) include all proposals submitted through the ZKsync [Token Governor](https://docs.google.com/document/d/1M2eq7oTw13XqEeVeBWcaDoBvmR-BdWRl3fYlFU8l-W4/edit?usp=sharing). Token Programs assign minting and burning rights of ZK tokens to specified capped minters, activating new mechanics to distribute the ZK token. All TPPs should be aligned with these guidelines to help achieve the goals supporting the vision of the ZK Credo.&#x20;

> ℹ️ Learn more about ZKsync strategic priorities by visiting the [ZKsync Governance North Star](https://docs.zknation.io/zk-nation/zksync-governance-system-north-star) and [GAP-1: ZKsync Token Program Priorities 2025 v1.0](https://vote.zknation.io/dao/proposal/13823050748058617424077595486689751986818771098977300222700522842013613046754?govId=eip155:324:0x496869a7575A1f907D1C5B1eca28e4e9E382afAb).

### What is a capped minter?

[Capped minters](capped-minters-101.md) are unique smart contracts of the ZKsync ecosystem that allow for “just-in-time minting.” Each capped minter is assigned a maximum number of tokens, known as the “cap,” which is allowed to be minted. Those with the minter role of a capped minter can mint tokens from that supply whenever they choose to, up to the maximum specified.&#x20;

How is this relevant for governance? Unlike other token launches, not all ZK tokens were minted upon the launch of the ZK token. In other words, there is no token treasury. Instead, the Token Assembly grants minting rights to administrators of Token Programs. The Token Assembly has access to 29.3% of the total token supply, as defined during the token launch. This design removes the risks associated with a large treasury and instead helps shift the agency of token management to the final token recipient.

> ℹ️ Learn more about the [benefits of capped minters](https://forum.zknation.io/t/understanding-key-benefits-of-capped-minters/686).

> ℹ️ Token Programs must use the [latest version of the ZK capped minter](https://forum.zknation.io/t/zk-capped-minter-v2-nested-minters-start-time-expiration-pause-and-cancel/417) (currently V2) contracts and factory. Once deployed, the contracts and admin multisig (if applicable) must have at least one security review by a Security Council member or reputable security firm.

### What is a token mechanic?

Token mechanics are a series of smart contracts executing ZK token allocations based on pre-determined, (onchain) verifiable criteria. A capped minter is the core building block to any token mechanic.&#x20;

Token mechanics programmatically enforce process rather than having to manually manage it. They also help reduce management multisig signer responsibilities & coordination.

> ℹ️ Learn more about token mechanics and TPP standards in the [TPP FAQ](https://forum.zknation.io/t/tpp-frequently-asked-questions/141).

### What information should I include in a TPP?

A ZK Token Program Proposal should include all the necessary information for ZKsync Delegates to make an informed decision and vote on the proposal. The proposal length and detail should align with the scale of the ZK Token mechanic and accountability measures.&#x20;

**All TPPs should include:**

* IMPACT: Describe how the token program will impact one of the [ZKsync Governance North Star metrics](https://docs.zknation.io/zk-nation/zksync-governance-system-north-star) and what metrics it will use to measure success. Please also reference other guiding documents such as a technical roadmap or annual priorities for the Token Assembly.
* MECHANIC: Token Programs should deploy self-executing smart-contracts that are designed to distribute tokens autonomously based on predefined conditions or metrics ("mechanics"). Every mechanic should support ZKsync adoption and innovation, and include the following:
  * A token model that describes how the mechanic uses and distributes ZK to achieve the Token Program objectives. Use this as a template to start with: “This TPP deploys a(n) \[Mechanic Type] smart-contract supporting \[North Star Metric] that allocates ZK tokens based on \[Onchain Action Eligibility/Metric]”
  * All allocations, including:
    * Program Rewards: ZK being distributed to qualifying participants
    * Proposal Success Rewards: Token allocations as a reward for code development, code audits, and coordination efforts leading to a successful vote on the proposal.
    * Mechanic Usage Fees: Token allocations necessary to cover the program’s smart contracts fees over the course of the program.
    * Administration: Token allocations related to SteerCo member participation, program monitoring, and other management.
    * Security Review: Token mechanics and capped minter structures should link to relevant security reviews and audits from Security Council members or another vetted organization.
* PLAN: Outline a long-term project plan (for example 6-months to 2+ years) with outcomes, milestones, and deliverables aligned to the ZKsync Governance North Star, endorsed ZKsync Strategic Priorities, and the ZK Credo.
  * Specify KPIs supporting those outcomes and the overarching vision of the Token Program. Include how those KPIs will be measured (e.g. onchain, elsewhere).
  * Explain the permissionless pathways available for public participation. For example, address questions like: how is the program composable?, what standards does it follow?, will there be a public communication channel?, and what projects are available for contributors?
* ACCOUNTABILITY FRAMEWORK: Specify what methods will hold the program, mechanic, operations, and participants accountable for their commitments. For example, this can include items such as a Steering Committee, Token Streaming Terms, staking, or contracting with ZKGPS (l[earn more here](https://forum.zknation.io/t/zkgps-advancing-accountability-in-proposal-execution/480)).

> ✍️ TEMPLATE: Proposal authors are encouraged to follow the [standard proposal template for Token Program Proposals](https://github.com/zksync-association/governance-resources/blob/main/proposal-templates/02_tpp_template_token_governor.md).\
> \
> ✍️ MULTISIG CONFIGURATION: All multisigs related to Token Programs must conform to industry best practice. [Multisig guidelines are available on the ZKsync Association Github repository for review.](https://github.com/zksync-association/governance-resources/blob/main/MultisigGuide_TokenProgram.md)

> ℹ️ _NOTE: All documentation should be included in the onchain proposal, or include links to an onchain source such as Arweave, IPFS, etc. This allows the proposal content to be public and accessible across web3 applications._

### Token Program Cancellation

A Token Program can be cancelled by the Token Assembly or the Token Program managers.

* **Onchain cancellation by Token Program managers:**
  * **Cancellation Process:** Program Managers deactivate capped minter contract according to its version:
    * **CappedMinterV1:** Transfer control of all capped minter admin multisigs to the burn address. To transfer control of a multisig to a burn address, propose a transaction that adds the burn address as the sole owner (0x0000000000000000000000000000000000000000). Then, in either the same or a following transaction, remove all signers except the burn address. Since no one controls the private key, no future actions are possible.
    * **CappedMinterV2:** Call the `cancel` method on the contract to permanently revoke all roles.
  * **Prior to onchain cancellation:** All final token disbursements, legal contracts review, and forum communications should be completed prior to on-chain cancellation.
    * **Forum Communication:** The Token Program manager should provide a clear rationale for the cancellation of the program via the official governance forum. The communication should include relevant timelines. Program cancellation plans should be shared a month in advance.
    * **Legal Contracts Review:** Token Program managers are responsible for liaising with the ZKsync Association and ZKGPS to review the program’s legal agreements. For example, to terminate applicable service-provider contracts.
    * **Final Disbursements:** Token Program managers must execute final disbursements for any work completed to date, ensuring distributions are made within a reasonable timeframe. All tokens minted under a Token Program's capped minter must be allocated according to the terms of that program. Unallocated minted tokens cannot be returned to the Token Assembly. Program managers should publish a detailed accounting report detailing all final allocations to all program service provider and token program participants.
* **Onchain cancellation by Token Assembly:**
  * **Cancellation Process:** Submit and execute a TPP onchain to revoke the ZK Token minter role from active capped minters for specific program. The proposal should provide a clear rationale for the cancellation of the program.
  * **Prior to onchain cancellation:**
    * **Forum Communication:** The ZKsync Delegate submitting the proposal should follow the standard guidelines in proposal submission, including publishing a forum post with the program cancellation proposal details.
    * **Legal Contracts Review:** If quorum is met and approval is expected, Token Program managers are responsible for liaising with the ZKsync Association and ZKGPS to review the program’s legal agreements. For example, to terminate applicable service-provider contracts.
    * **Final Disbursements**: If quorum is met and approval is expected, the Token Program managers are responsible for executing final disbursements for work-to-date prior to the execution of the cancellation proposal onchain. Upon execution of the cancellation proposal, no further tokens may be minted under the canceled Token Program. All tokens minted under a Token Program's capped minter must be allocated according to the terms of that program. Unallocated minted tokens cannot be returned to the Token Assembly. Program managers should publish a detailed accounting report detailing all final allocations to all program service provider and token program participants.
