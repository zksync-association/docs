# TPP FAQ

### What onchain actions can I deploy with a TPP?

Delegates need to include the appropriate onchain action in their proposal to successfully connect ZK tokens to a Token Program mechanic. An onchain action is represented by a hexadecimal value known as _calldata_. The calldata, or executable payload, instructs the ZKsync Token Governor Timelock (further details linked below) to give access to ZK Tokens.

The approval of a Token Program Proposal allows a specified address to mint ZK tokens (up to the capped amount) or mint and directly transfer them to a designated recipient. This is done by granting the MINTER role to the address of a designated capped minter via the Token Governor Timelock.

* **Minter Address Approval (most common):** Token Governor acts as MINTER\_ADMIN. The Delegate proposer specifies an address, such as a ZkCappedMinter contract, to act as MINTER. A specific agent (individual, entity, or autonomous code) represented by an Ethereum address can then mint tokens via the approved address.
* **Direct Mint:** Token Governor Timelock contract acts as MINTER. The Delegate proposer specifies the recipient of the ZK Token (\_mintReceiver) and the ZK Token amount (\_mintAmount). The Token Governor then mints tokens directly to that address.

For more information about the ZKsyncTokenGovernor, Timelock Contract, and ZK Token, you can visit [https://github.com/ZKsync-Association](https://github.com/ZKsync-Association).&#x20;

> ℹ️ Proposals will be removed from the ZKsync Governance Portal if they enable access to ZK tokens by prohibited addresses, including those associated with sanctioned entities, individuals, or jurisdictions, as well as addresses linked to illicit activities like fraud, money laundering, terrorist financing, or other criminal enterprises.

### **Onchain Action Example 1: Minter Address Approval for up to 100 ZK tokens**

Minter Address Approvals are expected to be the most common method to access ZK tokens. Minter Address Approvals allow specific mechanics to mint tokens on demand. By minting on demand, mechanics reduce dependencies on custodial services. Minting on demand can also have other benefits, such as reducing security risks, ensuring that the tokens have a clean history, and allowing recipients to choose the time and place of minting, which may help them clarify the tax treatment of their tokens.

**Example Proposal:**

1. Alice submits a Token Program Proposal for Minter Address Approval. If the proposal is approved, then “MechanicManager _can_ Mint _a maximum of_ 100 ZK”
   1. ZKTokenGovernor-Timelock acts as `MINTER_ADMIN` for ZK token contract ([ZKtokenV2.sol](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkTokenV2.sol))
   2. Mechanic\_ZKCappedMinter is set as `MINTER` role of ZKtokenV2.sol
   3. MechanicManager is set as `ADMIN` of Mechanic\_ZKCappedMinter
      1. Note: Capped Minter has immutable Cap, which cannot be changed by `ADMIN` or any other party
2. Alice's Token Program Proposal has calldata that:
   1. Calls `_grantRole` on ZKtokenV2.sol
   2. Assigns `MINTER_ROLE` to Mechanic\_ZKCappedMinter
      1. The Mechanic\_ZKCappedMinter is a separate smart contract deployed prior to proposal submission. To ensure quality of the smart contract, Mechanic\_ZKCappedMinter bytecode hash should match [https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkCappedMinterV2.sol](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkCappedMinterV2.sol). An example can be viewed on the [ZKsync Block Explorer](https://era.zksync.network/address/0x00D3dc9676572d04665A64Ee72A78cF0358F6382#code), using the [deployment logs](https://www.notion.so/FINAL-Token-Governor-Proposal-Submission-Guidelines-NEW-SUBPAGE-1d697013caf546dabbebb9f8aeaefecd?pvs=21) which specify the `ContractDeployed` event with `bytecodeHash`  of `0x0100007911f29707ff4a93ecdc84a682cbc3969469865c43bb233b35c3068b24`
      2. The Mechanic\_ZKCappedMinter parameters would be set as follows for this proposal:
         1. TOKEN = \[ZK Token Contract];
         2. ADMIN = MechanicManager;
         3. CAP = 100;
3. If Alice's proposal passes, then MechanicManager can mint 100 ZK tokens through the Mechanic\_ZKCappedMinter after the proposal transaction is executed onchain.

### **Onchain Action Example 2: Direct mint of 100 ZK tokens**

Direct minting should be used if the mechanic requires ZK tokens to be immediately minted. For example, a novel Token Program Proposal may require staked ZK tokens at inception, or swapping ZK tokens for another digital asset immediately upon proposal approval.

**Example Proposal:**

1. Alice submits a Token Program Proposal for Direct mint. If the proposal is approved, then “MechanicManager receives 100 ZK”
   1. ZKTokenGovernor-Timelock acts as `MINTER` for ZKtokenV2.sol
2. Alice's Token Program Proposal has calldata that:
   1. Sets `_mintReceiver` as MechanicManager
   2. Sets `_mintAmount` to `100`
   3. Calls `_mint(_mintReceiver, _mintAmount)`
3. If Alice's proposal passes, then MechanicManager receives 100 ZK tokens when the proposal is executed.
4. Should Alice be assigned the `ADMIN` role of the MechanicManager, then Alice can manage funds as specified in the MechanicManager.

> ℹ️ If you need support drafting the executable proposal code for your proposal, please reach out to the ZKsync Association for support at [forum.zknation.io](http://forum.zknation.io/).

### Are token programs the right channel to ask for grants?

Token programs are intended to be for mobilizing large and long-term mechanics, not grants. In other words, token programs should launch self-executing smart contract designed to distribute tokens autonomously based on predefined conditions or metrics. If you have an idea for a grant, transform it into a ZK token mechanic supporting a specific [ZKsync goal and KPI](https://docs.zknation.io/zk-nation/zksync-governance-system-north-star).

### What tools are available for token mechanics?

The ZK token is an ERC20 token and is compatible with common web3 tools. To better understand the possibilities in autonomous token flows, you can connect with organizations such as:

* Drips ([https://www.drips.network/](https://www.drips.network/))
* Hedgey ([https://hedgey.finance/](https://hedgey.finance/))
* Hats ([https://www.hatsprotocol.xyz/](https://www.hatsprotocol.xyz/))
* MetaLex ([https://www.metalex.tech/](https://www.metalex.tech/))
* Merkl ([https://merkl.angle.money/](https://merkl.angle.money/))
* Sablier ([https://sablier.com/](https://sablier.com/))
* Superfluid ([https://www.superfluid.finance/](https://www.superfluid.finance/))

> ℹ️ You can also check out the [TPP Builders](https://forum.zknation.io/c/token-mechanics/tpp-builders/43) section of [forum.zknation.io](http://forum.zknation.io) for more potential technical tools and partners for token mechanic development.&#x20;

### Can the Token Assembly change the total supply cap via a governance proposal?

* The ZKsync Token Assembly could submit a proposal through the Protocol Governor to propose to change the 21B ZK total supply cap.
