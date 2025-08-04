# ZKsync Governance Procedures: Overview

_Version published on 12 September 2024_

### 1. Introduction&#x20;

1. The ZKsync Governance Procedures describe the ZKsync governance system, which is responsible for the governance of the ZKsync protocol.
2. The ZKsync governance system includes standard and emergency response procedures along with specifications for governance bodies, namely the ZKsync Security Council and ZKsync Guardians.
3. The ZK token is a protocol token used within the ZKsync governance system to allocate and delegate voting power over governance proposals, and may have additional functionality in the future if approved pursuant to the process described in these Governance Procedures.
   1. The ZK token contract is deployed at [0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E](https://era.zksync.network/token/0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E) on ZKsync Era.
4. If there are changes made to the smart contracts, code and onchain mechanisms that comprise the ZKsync governance system, the ZKsync Governance Procedures will be updated to reflect such changes.&#x20;
   1. The ZKsync Association is expected to maintain and update these ZKsync Governance Procedures as necessary.&#x20;
   2. However, the ZKsync Association does not assume responsibility for the completeness of these Governance Procedures, which are intended to function as a high-level and readily-understandable description of the governance and the governance processes involved in the ZKsync Protocol. The Governance Procedures are incomplete because they relate and refer to smart contracts, code and onchain mechanisms that operate deterministically in accordance with their specifications. As such, the ZKsync Governance Procedures must only be read in conjunction with a thorough understanding of those smart contracts, code and onchain mechanisms, and the ZKsync Governance Procedures are not in themselves intended to be a comprehensive account of all relevant risks, uncertainties, adverse/negative facts and disclaimers relating to the governance and the governance processes involved in the ZKsync Protocol.

### 2. ZKsync Protocol

1. The ZKsync governance system is expected to govern smart contracts related to the ZKsync protocol, including but not limited to:
   1. DiamondProxy contract deployed at [0x32400084C286CF3E17e7B677ea9583e60a000324](https://etherscan.io/address/0x32400084C286CF3E17e7B677ea9583e60a000324) on Ethereum.
   2. Legacy ZKsync ERC20 Bridge deployed at [0x57891966931Eb4Bb6FB81430E6cE0A03AAbDe063](https://etherscan.io/address/0x57891966931Eb4Bb6FB81430E6cE0A03AAbDe063) on Ethereum.
   3. ZKsync ERC20 Bridge deployed at [0x11f943b2c77b743AB90f4A0Ae7d5A4e7FCA3E102](https://explorer.zksync.io/address/0x11f943b2c77b743AB90f4A0Ae7d5A4e7FCA3E102) on ZKsync.
   4. ZKsync Shared Bridge deployed at [0xD7f9f54194C633F36CCD5F3da84ad4a1c38cB2cB](https://etherscan.io/address/0xD7f9f54194C633F36CCD5F3da84ad4a1c38cB2cB) on Ethereum.&#x20;
   5. ZKsync beacon proxy deployed at [0x1Eb710030273e529A6aD7E1e14D4e601765Ba3c6](https://explorer.zksync.io/address/0x1Eb710030273e529A6aD7E1e14D4e601765Ba3c6) on ZKsync.
   6. ZKsync Validator Timelock deployed at [0xa8CB082A5a689E0d594d7da1E2d72A3D63aDc1bD](https://etherscan.io/address/0xa8CB082A5a689E0d594d7da1E2d72A3D63aDc1bD) on Ethereum.
   7. ZKsync Wrapped Ether contract deployed at [0x57891966931Eb4Bb6FB81430E6cE0A03AAbDe063](https://explorer.zksync.io/address/0x57891966931Eb4Bb6FB81430E6cE0A03AAbDe063) on ZKsync.

### 3. ZK Credo&#x20;

1. The [ZK Credo](https://docs.zknation.io/zk-nation/mission-zk-credo) sets out the vision and values of ZKsync.
   1. The role of ZKsync Guardians is to serve as protectors of the Mission (as defined in Schedule 4) of ZKsync, as set out in the ZK Credo.

### 4. Governance Bodies

1. The governance bodies that participate in the ZKsync governance system include:
   1. **Token Assembly**: The Token Assembly is a governance body made up of ZK tokenholders, who delegate the voting power of ZK tokens they hold, to ZKsync addresses in order to (indirectly) participate in the ZKsync governance system.
      1. The voting power of the Token Assembly is held and exercised by the controllers of the ZKsync addresses to which voting power has been delegated ("**Delegates**").
      2. ZK tokenholders can also delegate the voting power of their ZK tokens to themselves, by delegating to a ZKsync address they control.&#x20;
      3. Delegates may propose and vote on governance proposals.
   2. **ZKsync Security Council** ("**Security** **Council**"): The Security Council is a governance body currently made up of a minimum of nine (9) members out of twelve (12) allocated seats, whose powers, procedures, and membership is set out in Schedule 3: ZKsync Security Council.
      1. The Security Council controls the following Ethereum L1 multsig: [0x66E4431266DC7E04E7d8b7FE9d2181253df7F410](https://etherscan.io/address/0x66E4431266DC7E04E7d8b7FE9d2181253df7F410)
      2. The primary responsibility of the Security Council is to evaluate and approve Protocol Governor proposals (as defined below) that have been approved by Delegates, before the proposals are executed onchain.
      3. The Security Council can freeze the ZKsync protocol in case of an emergency.
      4. The Security Council can initiate and/or approve emergency upgrades, which will be executed subject to the additional approval of both the ZKsync Guardians and the ZKsync Foundation.
   3. **ZKsync Guardians** ("**Guardians**"): Guardians are a governance body who serve as protectors of the ZK Credo, made up of a minimum of five (5) individuals out of eight (8) allocated seats, whose powers, procedures, and membership are set out in Schedule 4: ZKsync Guardians.
      1. The Guardians control the following Ethereum L1 multsig: [0x600dA620Ab29F41ABC6596a15981e14cE58c86b8](https://etherscan.io/address/0x600dA620Ab29F41ABC6596a15981e14cE58c86b8)
      2. Guardians have the independent power to veto governance proposals that are inconsistent with the ZK Credo. This includes the power to veto governance proposals that are abusive, malicious or could otherwise adversely affect ZKsync or its governance system. The Guardians' decisions are made at their sole discretion.&#x20;
      3. The Guardians are not required to assess the legality of governance proposals.
      4. Guardians may evaluate and approve Protocol Governor proposals, approved by Delegates, if the Security Council, for any reason, abstain from exercising their approval during the Risk Review Period.&#x20;
      5. Guardians can approve Emergency Upgrades, which will be executed subject to the additional approval of the Security Council and the ZKsync Foundation.

### 5. Supporting Entities

1. **ZKsync Foundation**: The ZKsync Foundation is a Cayman foundation that, among other things, provides grants and enters into agreements with a diverse range of (potentially competing) market participants each of whom are working on or in relation to ZKsync, ZKsync related technology, the Ethereum 'layer-1' blockchain system or other zero-knowledge based cryptographic technology more widely, including for the purposes of studying, evaluating, testing, monitoring, maintaining, facilitating, fostering and improving the use or functionality of ZKsync and ZKsync related technology.
   1. The ZKsync Foundation controls the following Ethereum L1 multisig ("**ZKsync Foundation Multisig**"): [0xbC1653bd3829dfEc575AfC3816D4899cd103B51c](https://etherscan.io/address/0xbC1653bd3829dfEc575AfC3816D4899cd103B51c)
   2. The ZKsync Foundation can approve Emergency Upgrades, which will be executed subject to the approval of both the ZKsync Guardians and the ZKsync Security Council.&#x20;
2. **ZKsync Association**: The ZKsync Association is an Austrian association (Verein) ("**ZKsync Association**") that is primarily responsible for: (i) designing the ZKsync governance system; (ii) deploying the initial governance and token smart contracts; (iii) appointing the initial members of the governance bodies described below; (iv) conducting the ZK token airdrop; (v) supporting the ongoing governance of the ZKsync protocol as contemplated by its governing documents (e.g., by periodically updating these Governance Procedures); and (vi) removing content on the following interfaces that, at its sole discretion, violates or conflicts with Austrian law or could result in negative tax consequences:&#x20;
   1. The ZKsync Governance Portal available at [https://vote.zknation.io](https://vote.zknation.io) and [https://delegate.zknation.io](https://delegate.zknation.io).&#x20;
   2. The ZK Nation Governance Documentation available at [https://docs.zknation.io](https://docs.zknation.io).
   3. The ZKsync Governance Forum available at [https://forum.zknation.io](https://forum.zknation.io).&#x20;

### 6. Standard Governance Procedures

1. The standard procedure for governance proposals voted on by Delegates using the voting power conveyed by the ZK token and executed by smart contracts deployed for the purpose of decentralized onchain governance (such smart contracts, "**Governors**") are set out in Schedule 1: Standard Governance Procedures.
2. There are three (3) Governors in the ZKsync governance system, each of which is responsible for a specific type of governance proposal:
   1. **Protocol Governor**: responsible for executing ZKsync Improvement Proposals ("**ZIPs**") that upgrade the ZKsync protocol and/or components of the ZKsync governance system.&#x20;
      1. The Protocol Governor is an OpenZeppelin smart contract deployed on ZKsync Era: [0x76705327e682F2d96943280D99464Ab61219e34f](https://explorer.zksync.io/address/0x76705327e682F2d96943280D99464Ab61219e34f)
      2. The Protocol Governor Timelocks is an OpenZeppelin smart contract deployed on ZKsync Era: [0x085b8B6407f150D62adB1EF926F7f304600ec714](https://explorer.zksync.io/address/0x085b8B6407f150D62adB1EF926F7f304600ec714)
   2. **Token Governor**: responsible for executing Token Program Proposals ("**TPPs**") that assign minting and burning rights of ZK tokens for token programs that are aligned with the Token Program Guidelines, and help achieve the goals supporting the vision of the ZK Credo.
      1. The Token Governor is an OpenZeppelin smart contract deployed on ZKsync Era: [0xb83FF6501214ddF40C91C9565d095400f3F45746](https://explorer.zksync.io/address/0xb83FF6501214ddF40C91C9565d095400f3F45746)
      2. The Token Governor Timelock is an OpenZeppelin smart contract deployed on ZKsync Era: [0xe5d21A9179CA2E1F0F327d598D464CcF60d89c3d](https://explorer.zksync.io/address/0xe5d21A9179CA2E1F0F327d598D464CcF60d89c3d)
   3. **GovOps Governor**: responsible for facilitating Governance Advisory Proposals ("**GAPs**") related to governance and operations that do not have direct onchain consequences.
      1. The GovOps Governor is an OpenZeppelin smart contract deployed on ZKsync Era: [0xEEEa739a8b6fB1b8f703E23C9Be03CeeA643b160](https://explorer.zksync.io/address/0xEEEa739a8b6fB1b8f703E23C9Be03CeeA643b160)
      2. The GovOps Governor Timelock is an OpenZeppelin smart contract deployed on ZKsync Era: [0xC9E442574958f96C026DeF9a50C3236cab17428a](https://explorer.zksync.io/address/0xC9E442574958f96C026DeF9a50C3236cab17428a)

### 7. Emergency Response Procedures

1. Procedures for executing a protocol upgrade to the ZKsync protocol to address threats that pose immediate security risks to the ZKsync ecosystem and/or the ZKsync governance system are set out in Schedule 2: Emergency Response Procedures.
2. There are two (2) types of Emergency Responses that can be executed in the ZKsync governance system:
   1. Freeze of Layer 1 contracts; and/or
   2. Execution of an Emergency Upgrade.
3. The three (3) governance bodies involved in initiating and/or approving Emergency Upgrades with their respective multisigs ("**Emergency Upgrade Signers**") are the:
   1. Security Council;
   2. Guardians; and&#x20;
   3. ZKsync Foundation.
4. Each Emergency Upgrade Signer is represented in the ZKsync governance system by a multisig which is made up of Signers. As used in these Governance Procedures, "**Signer**" means (1) a multisig wallet or (2) an externally owned account (EOA).

### 8. Legal&#x20;

1. These Governance Procedures are provided for informational purposes only, are not a binding legal agreement, and may be changed prior to launch of the ZKsync governance system to address security vulnerabilities or similar matters.
2. Upon its launch, the ZKsync governance system is not controlled by the ZKsync Association or any third-party entity, but requires the approval of the Token Assembly to decide and make any changes or updates to the ZKsync protocol. The ZKsync Association will make good faith efforts to reflect any changes or updates to the ZKsync governance system in these ZKsync Governance Procedures. However, there is no guarantee of up-to-dateness or completeness.
3. In the event of a conflict between these ZKsync Governance Procedures and any agreement or obligation entered into by any person or entity in connection with the matters described herein, including the code referred to in these ZKsync Governance Procedures, such agreement or obligation, or the relevant code shall control in all respects.
4. These ZKsync Governance Procedures are subject to the Risk Factors and Disclaimers described [here](https://docs.zknation.io/legal/risk-factors-and-disclaimers), which are incorporated by reference in their entirety as if set forth herein.
5. Nothing herein shall create, or be construed as creating, between or among any person or entity described herein and any other person or entity (except as may be expressly agreed by the applicable parties in writing): (1) an agency or fiduciary relationship, or any assumption of duty or responsibility, (2) a service or employment relationship, or (3) a joint enterprise, business opportunity relationship, partnership, unincorporated association or similar relationship.
