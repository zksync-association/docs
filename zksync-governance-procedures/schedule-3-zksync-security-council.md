# Schedule 3: ZKsync Security Council

### 1. Overview

1. The Security Council is a governance body designed to safeguard the security of the ZKsync protocol (ZKsync ERA, ZKsync Chains, and other components of ZKsync) and components of the ZKsync ecosystem governed by Protocol Governor proposals.&#x20;
2. The Security Council consists of 12 technical experts ("**Security Council Members**") who are Signers (as defined in the Overview) of a multisig wallet ("**Security Multisig**") that has the power to perform certain standard and emergency actions (Emergency Responses) related to the ZKsync protocol as part of the ZKsync governance system.
3. The address of the Security Multisig, which is deployed on Ethereum, is: [0x66E4431266DC7E04E7d8b7FE9d2181253df7F410](https://etherscan.io/address/0x66E4431266DC7E04E7d8b7FE9d2181253df7F410).

### 2. Security Council Membership

1. Legal
   1. Legal obligations of Security Council Members are governed by (1) contractual agreements entered into between the Security Council Members and the ZKsync Security Council entity; and (2) the bylaws of the ZKsync Security Council entity (to which the Security Council Members agree to be bound).
   2. The ZKsync Security Council entity bylaws can be found [here](https://drive.google.com/file/d/1W5Z5rodkG9lEGIGVT3HSBQ7Foeed4mYL/view?usp=sharing).
2. Security Council Members
   1. The following 12 entities and individuals are members of the Security Council:
      1.  aleph\_v&#x20;

          0x9B39Ea22e838B316Ea7D74e7C4B07d91D51ccA88
      2. Chainlight, represented by Tim Becker\
         0x84BF0Ac41Eeb74373Ddddae8b7055Bf2bD3CE6E0
      3. Cyfrin, represented by Mark Scrine\
         0x35eA56fd9eAd2567F339Eb9564B6940b9DD5653F
      4. Dedaub, represented by Neville Grech\
         0xB7aC3A79A23B148c85fba259712c5A1e7ad0ca44
      5. Mariano Conti \
         0x725065b4eB99294BaaE57AdDA9c32e42F453FA8A
      6. Matter Labs, represented by Vlad Bochok\
         0xc3Abc9f9AA75Be8341E831482cdA0125a7B1A23e
      7. Nethermind, represented by Mauricio Cortes\
         0x69462a81ba94D64c404575f1899a464F123497A2
      8. Open Zeppelin, represented by Juan Bautista Carpanelli\
         0x34Ea62D4b9bBB8AD927eFB6ab31E3Ab3474aC93a
      9. Peckshield, represented by Xuxian Jiang\
         0xFB90Da9DC45378A1B50775Beb03aD10C7E8DC231
      10. Spearbit, represented by Mike Leffer\
          0x9B8Be3278B7F0168D82059eb6BAc5991DcdfA803
      11. Yev Broshevan\
          0x13f07d9BF17615f6a17F272fe1A913168C275A66
      12. Yoav Weiss\
          0x3888777686F0b0d8c3108fc22ad8DE9E049bE26F
3. Term
   1. Security Council Members will serve on the Security Council until they are removed or replaced.&#x20;
4. Removal of Security Council Members
   1. A Protocol Governor proposal, approved by Delegates, is required to remove a Security Council Member from the Security Council as a Signer of the Security Multisig.&#x20;
   2. In exceptional circumstances, a Security Council Member may be removed from the Security Council and Security Multisig by an Emergency Upgrade, which requires the approval of the Emergency Upgrade Multisig.
5. Replacement and Addition of Security Council Members
   1. The Board of the ZKsync Security Council Foundation will recommend candidates to replace any Security Council Members that have been removed from the Security Council and Security Multisig, and may use the GovOps Governor as part of this process.
   2. A Protocol Governor proposal, approved by Delegates, is required to be passed in order to add new Security Council Members to the Security Multisig.&#x20;
   3. In exceptional circumstances, where there is a security threat and the period of time required to submit a Protocol Governor proposal is considered by Guardians to put the Mission of the ZK Credo at risk, Security Council Members may be added to the Security Council and Security Multisig by an Emergency Upgrade, which requires the approval of the Emergency Upgrade Multisig.

### 3. Emergency Responses

1. Power to freeze
   1. The Security Council has the power to freeze the ZKsync protocol, or parts thereof, for various periods of time, in response to imminent or active security threats, such as critical bugs or exploits, that could jeopardize the integrity of the ZKsync protocol.
   2. A Soft Freeze, which initiates a freeze for twelve (12) hours, requires approval from three (3) Security Council Members.
      1. The signature threshold for a Soft Freeze (between one (1) and nine (9) Signers) may be adjusted at the sole discretion of Security Council Members, with the approval of nine (9) Signers on the Security Multisig.
   3. A Hard Freeze, which initiates a freeze for seven (7) days, requires approval from nine (9) Security Council Members.&#x20;
   4. While the ZKsync protocol is frozen, only an Emergency Upgrade may be executed to address the threat.
   5. After a Soft Freeze and a Hard Freeze have been initiated, an Emergency Upgrade must be passed before any subsequent freezes may be initiated.
   6. Once frozen, an Emergency Upgrade may be executed in order to remove the freeze and/or initiate a subsequent freeze.
2. Power to unfreeze
   1. After a Soft Freeze and/or a Hard Freeze has been initiated, the Security Council may unfreeze (“Unfreeze”) the contracts at their discretion, with the approval of nine (9) Signers on the Security Multisig.
3. Emergency Upgrade
   1. Any Security Council Member may initiate an Emergency Upgrade without the express approval of the Token Assembly in response to a security threat.
   2. In order to pass an Emergency Upgrade, approval is required from Emergency Upgrade Multisig (i.e., nine (9) Signers on the Security Multisig, along with five (5) Signers on the Guardian Multisig, and three (3) Signers on the ZKsync Foundation Multisig.

### 4. Non-Emergency Actions

1. If a Protocol Governor proposal is approved by Delegates, the proposal progresses to a three (3) day Timelock Period during which time Guardians can exercise an Offchain Veto of the proposal ("**Offchain Veto Period**").&#x20;
2. If Guardians exercise their veto during the Offchain Veto Period, with a minimum of five (5) Guardians transmitting an offchain signed statement to the ZKsync Security Council Foundation stating they are exercising their veto power, the Security Council shall abstain from approving the Protocol Governor proposal in the Risk Review Period.
   1. With approval from any two (2) individual Guardians, the Offchain Veto Period may be extended from three (3) days to seven (7) days, if the extension is executed in the first three (3) days of the Offchain Veto Period.
3. If Guardians do not exercise their veto during the Offchain Veto Period, the proposal will progress to a 30-day period that commences at the end of the Offchain Veto Period, during which time the proposal must be approved by either the Security Council or Guardians in order to progress ("**Risk Review Period**").
4. It is the responsibility of the Security Council to evaluate all Protocol Governor proposals that progress to the Risk Review Period,  provided the Guardians have not exercised their Offchain Veto Power on a given proposal.
5. The signing threshold for the Security Multisig to approve a Protocol Governor proposal during the Risk Review Period is six (6) Signers on the Security Multisig.
6. Upon reaching the signing threshold of the Security Multisig, approval of the Protocol Governor proposal by the Security Council may be executed immediately, progressing the proposal to the 24-hour Timelock Period before execution.
7. If the Security Council, for any reason, is unwilling or unable to approve a Protocol Governor proposal during the Risk Review Period, Guardians can approve the Protocol Governor proposal during this period, and execution (with Timelock Period) of this approved proposal will be initiated at the end of the 30-day Risk Review Period.

