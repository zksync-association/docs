# Schedule 4: ZKsync Guardians

### 1. Overview

1. The [ZK Credo](https://github.com/zksync/credo) sets out the vision and values of ZKsync ("**the Mission**"). The Mission is protected by Guardians, who have the independent power to veto governance proposals that are inconsistent with the ZK Credo. This includes the power to veto governance proposals that are abusive, malicious or could otherwise adversely affect ZKsync or its governance system. The Guardians' decisions are made at their sole discretion.&#x20;
   1. The Guardians are not required to assess the legality of governance proposals.
   2. For the powers of the ZKsync Association with respect to content (e.g. proposals) related to the ZKsync governance system shown on its controlled online interfaces, please refer to Section 5.2.
2. Guardians are a governance body consisting of eight (8) individuals who are Signers (as defined in the ZKsync Governance Procedures: Overview) of a multisig wallet ("**Guardian Multisig**") that has the ability to exercise veto powers and approve Protocol Governor proposals during the Risk Review Period, and approve Emergency Responses related to the ZKsync protocol.
3. The address of the Guardian Multisig, which is deployed on Ethereum, is: [0x600dA620Ab29F41ABC6596a15981e14cE58c86b8](https://etherscan.io/address/0x600dA620Ab29F41ABC6596a15981e14cE58c86b8).

### 2. Membership&#x20;

1. Legal
   1. Legal obligations of Guardians are governed by the bylaws of the ZKsync Guardians entity.
   2. The bylaws of the ZKsync Guardians entity can be found [here](https://drive.google.com/file/d/1D_xkc1YeB46x1r8MnN2Sy-_1CurqP7y3/view?usp=sharing).
2. Members
   1. The following eight (8) individuals are Guardians:
      1. Juan Benet \
         0x55c671BcE13120387Ded710A1d1b80C0e3d8E857
      2. Alex Gluchowski \
         0x6D26874130A174839b9cd8CB87Ed4E09D0c1a5f0
      3. Bartek Kiepuszewski \
         0x015318c16AE443a20DE0A776dB06a59F0D279057
      4. pcaversaccio \
         0xCe7a3dFcc35602155809920Ff65e093aa726f6cf
      5. Gabriel Shapiro \
         0x178D8Eb1A1fb81B5102808A83318Bb04C6a9fC6D
      6. Awa Sun Yin \
         0x2A90830083C5Ca1f18d7AA7fCDC2998f93475384
      7. Aleksandr Vlasov \
         0x590926dBCDfD19627c3BbD2A6Eb96DeC7a3AbF69
      8. Eric Wall \
         0x538612F6eba6ff80FBD95D60dCDee16b8FfF2c0f
3. Term
   1. Guardians will act as Signers on the Guardian Multisig until they are removed or replaced in accordance with the specifications in this schedule.&#x20;
4. Removal of Guardians&#x20;
   1. Guardians may be removed from the Guardian Multisig by passing a Protocol Governor proposal (it being understood that Guardians have veto power over such proposals).
5. Replacement of Guardians
   1. Guardians will recommend candidates to replace any Guardian that is removed from the Guardian Multisig.
   2. A Protocol Governor proposal, approved by Delegates, is required to be executed (i.e. no Offchain Veto is passed) in order to replace a Guardian on the Guardian Multisig.&#x20;

### 3. Veto Powers

1. When Guardians exercise either an Onchain Veto or an Offchain Veto (as defined below), they are required, as a governance body, to communicate a justification for their actions in the ZKsync Forum (https://forum.zknation.io) within 48-hours of exercising a veto.&#x20;

### 4. Onchain Veto&#x20;

1. The Guardians may exercise an onchain veto on any proposal submitted to the Token Governor or the GovOps Governor ("**Onchain Veto**").
2. With the signatures of five (5) Signers on the Guardian Multisig, the Guardians have the power to execute an Onchain Veto by calling the cancel function from the Guardian Multisig, which means the proposal cannot progress towards execution.
3. The Onchain Veto may be exercised during the Vote Delay Period or during the Voting Period on the relevant Governor.

### 5. Offchain Veto

1. An offchain veto, communicated as a digitally signed written statement transmitted to the Security Council by electronic messaging ("**Offchain** **Veto**"), may be exercised with respect to any proposal or group of proposals submitted to the Protocol Governor.&#x20;
2. Guardians may also exercise their veto in relation to proposals submitted to the Protocol Governor that affects the Guardians themselves.
3. With a written statement signed by five (5) Guardians, the Guardians may exercise an Offchain Veto by communicating the signed statement to the ZKsync Security Council Foundation.
4. The Offchain Veto may be exercised at any time during the three (3) day Timelock Period that commences at the end of the Voting Period for a proposal that has been approved by Delegates on the Protocol Governor ("**Offchain Veto Period**").
5. With the signatures of two (2) Signers on the Guardian Multisig, the Guardians may execute an onchain transaction to extend the Offchain Veto Period from three (3) days to seven (7) days, if the extension is executed within the first three (3) days of the Offchain Veto Period.

### 6. Risk Review

1. With the approval of five (5) Signers on the Guardian Multisig, the Guardians may approve a Protocol Governor proposal during the Risk Review Period, as defined in Schedule 3: ZKsync Security Council, if the Security Council, for any reason, is unwilling or unable to approve the proposal.
2. Where Guardians approve a Protocol Governor proposal during the Risk Review Period, that approval will be executed onchain 30 days after the Risk Review Period commences.

### 7. Emergency Upgrades

1. The Guardian Multisig is one (1) of three (3) Signers required to approve an Emergency Upgrade.&#x20;
2. Any individual Guardian is able to submit an Emergency Upgrade for onchain approval, provided the intention of the Emergency Upgrade is to protect the Mission.&#x20;
3. An Emergency Upgrade requires onchain approval from five (5) Signers on the Guardian Multisig, along with approvals from the Security Multisig and the ZKsync Foundation Multisig, in order to be executed.&#x20;

