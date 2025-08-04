# Schedule 2: Emergency Response Procedures

### 1. Overview

1. Emergency Response Procedures detail the Emergency Responses that may be initiated and/or executed by specific governance bodies, to respond to security threats presented to the ZKsync protocol and/or the ZKsync governance system.&#x20;
2. There are two emergency responses that may be executed within the ZKsync governance system:
   1. Freeze of Layer 1 contracts; and/or
   2. Emergency Upgrade (as defined below, each or together referred to as "**Emergency Response**" or "**Emergency Responses**").
3. The Security Council is responsible for the identification and/or confirmation of certain circumstances that may require an Emergency Response to be taken.&#x20;
4. Once the Security Council has classified a threat sufficient to invoke the Emergency Response Procedures, it may initiate a freeze and/or Emergency Upgrade to neutralize the threat.

### 2. Freeze

1. The Security Council may freeze any smart contracts which make up the ZKsync protocol, for differing periods of time.
   1. A twelve (12) hour freeze may be initiated with the execution of an onchain transaction that is approved by three (3) Signers (as defined in the Overview) on the Security Multisig ("**Soft Freeze**").
      1. With the approval of nine (9) Signers on the Security Multisig, the signing threshold for a Soft Freeze may be changed by the Security Multisig to require a minimum of one (1) Signer and a maximum of nine (9) Signers.
   2. A seven (7) day freeze may be initiated with an onchain transaction approved by nine (9) Signers on the Security Multisig ("**Hard Freeze**").
2. After a Soft Freeze and/or a Hard Freeze has been initiated, the Security Council may unfreeze (“Unfreeze”) the contracts at their discretion, with the approval of nine (9) Signers on the Security Multisig.
3. After a Soft Freeze and a Hard Freeze have been initiated, an Emergency Upgrade must be passed before any subsequent freezes may be initiated.&#x20;
4. Once frozen, if an Emergency Upgrade is executed the freeze is removed
5. Once frozen, an Emergency Upgrade is required to initiate a subsequent freeze
6. If freeze period expires, anyone may unfreeze the protocol

### 3. Emergency Upgrade

1. An upgrade can be executed by a multisig that calls an upgrade on the ProtocolUpgradeHandler contract ("**Emergency Upgrade Multisig**"), which does not require the approval of the Token Assembly ("**Emergency Upgrade**").
2. The Emergency Upgrade Multisig requires the approval of the multisig of all three governance bodies who are signers on the Emergency Upgrade Multisig ("**Emergency Upgrade Signers**").
3. The Emergency Upgrade Signers are:
   1. Security Council;
   2. Guardians; and
   3. ZKsync Foundation.
4. An Emergency Upgrade may be initiated by any address.&#x20;
5. In order to execute an Emergency Upgrade with the Emergency Upgrade Multisig, all three (3) Emergency Upgrade Signers must each reach the signing threshold on their respective multisig.&#x20;
   1. The signing threshold for the Security Multisig to approve an Emergency Upgrade on the Emergency Upgrade Multisig is nine (9) Signers.
   2. The signing threshold for Guardian Multisig to approve an Emergency Upgrade on the Emergency Upgrade Multisig is five (5) Signers.
   3. The signing threshold for the ZKsync Foundation Multisig to approve an Emergency Upgrade on the Emergency Upgrade Multisig is three (3) Signers.
6. An Emergency Upgrade may be executed, whether a freeze is active or not, with sufficient approval from the Emergency Upgrade Multisig.&#x20;
7. An Emergency Upgrade during a freeze may include a message executed solely for the purpose of allowing the Security Council to initiate a subsequent freeze.
