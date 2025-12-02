# Schedule 1: Standard Governance Procedures

### 1. Overview

1. "**Standard Governance Procedures**" refer to the governance processes related to the three (3) Governor smart contracts that govern elements of ZKsync protocol and the ZKsync governance system, as voted on by Delegates using the voting power conveyed by the ZK token.&#x20;

### 2. Protocol Governor

1. The Protocol Governor is a smart contract deployed on ZKsync Era.
2. The Protocol Governor allows for the delegated voting power conveyed by the ZK token to be used to vote on ZKsync Improvement Proposals ("[**ZIPs**](https://docs.zknation.io/zksync-governance-proposals/zksync-improvement-proposals-zips)"), which are queued for permissionless execution on Ethereum if passed.&#x20;
3. Protocol Governor proposals are executed through the transmission of a message from ZKsync Era to Ethereum. Proposals are required to contain a hash of the proposal specification, which may then be executed on Ethereum.
4. The Protocol Governor is responsible for executing proposals related to:
   1. ZKsync Era protocol upgrades;&#x20;
   2. ZKsync network upgrades;&#x20;
   3. Upgrades to the Protocol Governor, Token Governor, and GovOps Governor;&#x20;
   4. Upgrades to the ZK token contract;
   5. Upgrades to the Security Multisig (i.e. to the Security Council and Security Council Members); and&#x20;
   6. Upgrades to the Guardian Multisig (i.e. to the Guardians and Guardian members).

### 3. Protocol Governor Proposal Process

1. The [proposal and voting process](https://docs.zknation.io/zksync-governance-proposals/zksync-improvement-proposals-zips#proposal-process-timeline) for the Protocol Governor is set out below.
2. **Proposal Submission**: Any Delegate who meets the proposal threshold is able to submit a proposal to the Protocol Governor via the [ZKsync Governance Portal](https://vote.zknation.io/dao) or any other interface connected to the Protocol Governor.
   1. The proposal threshold required for a Delegate to submit a proposal to the Protocol Governor is 0.1% (or 21 million) of the total number of ZK tokens that may be minted (currently 21 billion). &#x20;
3. **Vote Delay Period:** Upon submission, a proposal enters a three (3) day vote delay period, prior to the commencement of the Voting Period. "Voting Period", as referred to herein, means the period during which Delegates can submit their onchain votes to a submitted proposal.
   1. A proposal may be cancelled during the Vote Delay Period by the proposer, at their discretion.
4. **Voting Period**: The Voting Period for a Protocol Governor proposal is seven (7) days.
   1. Protocol Governor proposals have a quorum requirement of 3.0% (or 630 million) of the total number of ZK tokens that may be minted (currently 21 billion) and require a simple majority of the total number of "for" and "against" votes (i.e., casted votes without considering abstentions) to pass.
   2. If a vote causes quorum to be reached within the last 3 days of the voting period, the proposal's voting period is extended by 3 days from the point quorum is met.
5. **ZKsync Era Proposal Execution**: Upon approval by Delegates, a Protocol Governor proposal is executed on ZKsync Era through the transmission of a message from ZKsync Era to the _ProtocolUpgradeHandler_ contract on Ethereum.
6. **Offchain Veto Period**: Once an approved Protocol Governor proposal has been executed on ZKsync Era, the proposal will proceed to a three (3) day Timelock Period on Ethereum, during which time Guardians have the ability to exercise an Offchain Veto as described in Schedule 4: ZKsync Guardians. A "Timelock Period", as referred to herein, means a predetermined time delay imposed on approved governance proposals, during which a proposal cannot progress to the next stage of the proposal process.
   1. The Offchain Veto Period on the Protocol Governor is a three (3) day period that commences at the end of the Voting Period, if a proposal is approved.
   2. If an Offchain Veto is exercised, the written veto must be signed (including by electronic means) by at least five (5) of the Guardians (or a majority of the Guardians, if fewer than five) and for each Guardian, countersigned by an independent legal counsel or other person subject to recognized professional codes of conduct, and transmitted to a director or officer of the ZKsync Security Council Foundation.
   3. The Guardian Multisig can extend the Offchain Veto Period from three (3) days to seven (7) days, with the approval of any two (2) Signers (as defined in the Overview) on the Guardian Multisig.
7. If an Offchain Veto is exercised by the Guardians during the Offchain Veto Period, the proposal will not be approved by the Security Council or Guardians during the Risk Review Period, and after thirty (30) days the proposal will be canceled.&#x20;
8. **Risk Review Period**: If an Offchain Veto is not exercised by the Guardians during the Offchain Veto Period, the proposal progresses to the Risk Review Period, where the Security Council is required to (1) complete technical reviews of all necessary code relevant to the proposal, and (2) approve the proposal unless technical deficiencies are identified.
   1. During the 30 -day Risk Review Period, the proposal can only progress towards final execution if approved by the Security Council, or Guardians.
      1. If the Security Council approves a proposal during the Risk Review Period, the proposal immediately progresses to the Timelock Period described below.
      2. Guardians can approve a proposal during the Risk Review Period if the Security Council is unable or unwilling to approve the proposal, however the proposal will not proceed to the Timelock Period until the end of the 30-day Risk Review Period.
      3. If neither the Security Council nor Guardians approve a proposal during the Risk Review Period, the proposal will be canceled at the end of the 30-day period (i.e. the proposal will not progress to final execution).
9. **Timelock Period**: Upon successful approval during the Risk Review Period, the proposal proceeds to a 24-hour Timelock Period.&#x20;
10. **Final Execution**: Following the expiration of the Timelock Period, the proposal is queued for permissionless execution on Ethereum. &#x20;

### 4. Token Governor

1. The Token Governor is a smart contract deployed on ZKsync Era.&#x20;
2. The Token Governor allows for the delegated voting power conveyed by the ZK token to be used to vote on proposals related to assigning minting and burning rights for ZK tokens allocated to Token Programs.
3. Token Program Proposals ("[**TPPs**](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps)") must be made in accordance with the Token Program Guidelines, and help achieve the goals supporting the vision of the ZK Credo.
4. Token Governor proposals can be executed on ZKsync Era if passed in accordance with the proposal process below.

### 5. Token Governor Proposal Process

1. The [proposal process](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps#proposal-process-timeline) for a Token Governor is set out below.
   1. **Proposal Submission**: Any Delegate who meets the proposal threshold is able to submit a proposal to the Token Governor, which is deployed on ZKsync Era, as well as the ZKsync Foundation Multisig, which has a signing threshold of three (3) Signers.&#x20;
      1. The proposal threshold required for a Delegate to submit a proposal to the Token Governor is 0.1% of the total number of ZK tokens that may be minted (currently 21 billion).
      2. A proposal may be submitted via the [ZKsync Governance Portal](https://vote.zknation.io/dao) or any other interface connected to the Token Governor.
   2. **Vote Delay Period**: Upon submission, a proposal enters a three (3) day vote delay period, prior to the commencement of the Voting Period.
      1. A proposal may be cancelled during the Vote Delay Period by Guardians, if they choose to exercise their Onchain Veto as set out in _Schedule 4: ZKsync Guardians_.&#x20;
   3. **Voting Period**: The Voting Period for Token Governor proposals is seven (7) days.
      1. Token Governor proposals have a quorum requirement of 3.0% (or 630 million) of the total number of ZK tokens that may be minted (currently 21 billion) and require a simple majority of the total number of "for" and "against" votes (i.e., casted votes without considering abstentions) to pass.
      2. If a vote causes quorum to be reached in the last 2 days of the voting period, the proposal's voting period is extended 2 days from the point quorum is met.
      3. A proposal may be cancelled during the Voting Period by Guardians, if they choose to exercise their Onchain Veto as set out in _Schedule 4: ZKsync Guardians_. &#x20;
   4. **Timelock Period**: If an Onchain Veto is not exercised by the Guardians during the Onchain Veto Period, and the proposal is approved by Delegates, the proposal progresses to a 3-day Timelock Period.&#x20;
   5. **Execution**: Following the expiration of the Timelock Period, the proposal is queued for permissionless execution on ZKsync Era.&#x20;

### 6. GovOps Governor

1. The GovOps Governor is a smart contract deployed on ZKsync Era.
2. The GovOps Governor allows for the delegated voting power conveyed by the ZK token to be used to vote on Governance Advisory Proposals ("[**GAPs**](https://docs.zknation.io/zksync-governance-proposals/governance-advisory-proposals-gaps)"), that do not have direct onchain consequences.
3. The GovOps Governor is responsible for proposals related to offchain governance and/or operations of the ZKsync governance system.

### 7. GovOps Governor Proposal Process

1. The [proposal process](https://docs.zknation.io/zksync-governance-proposals/governance-advisory-proposals-gaps#proposal-process-timeline) for the GovOps Governor is set out below.&#x20;
   1. **Proposal Submission**: Any Delegate who meets the proposal threshold is able to submit a proposal to the GovOps Governor.
      1. The proposal threshold required for a Delegate to submit a proposal to the GovOps Governor is 0.1% of the total number of ZK tokens that may be minted (currently 21 billion).
      2. A proposal may be submitted via the [ZKsync Governance Portal](https://vote.zknation.io/dao) or any other interface connected to the GovOps Governor.
   2. **Vote Delay Period**: Upon submission, a proposal enters a three (3) day vote delay period, prior to the commencement of the Voting Period.
      1. A proposal may be cancelled during the Vote Delay Period by Guardians, if they choose to exercise their Onchain Veto as set out in _Schedule 4: ZKsync Guardians_.&#x20;
   3. **Voting Period**: The Voting Period for GovOps Governor proposals is seven (7) days.
      1. GovOps Governor proposals have a quorum requirement of 3.0% (or 630 million) of the total number of ZK tokens that may be minted (currently 21 billion) and require a simple majority of the total number of "for" and "against" votes (i.e., casted votes without considering abstentions) to pass.
         1. If a vote causes quorum to be reached in the last 2 days of the voting period, the proposal's voting period is extended 2 days from the point quorum is met.
         2. A proposal may be cancelled during the Voting Period by Guardians, if they choose to exercise their Onchain Veto as set out in _Schedule 4: ZKsync Guardians_.&#x20;
   4. **Timelock Period**: If an Onchain Veto is not exercised by the Guardians during the Onchain Veto Period, and the proposal is approved by Delegates, the proposal progresses to a 3-day Timelock Period.
   5. **Execution**: Following the expiration of the Timelock Period, the proposal may be executed, offchain or onchain, at the discretion of the proposer or parties named in the specification of the proposal.



