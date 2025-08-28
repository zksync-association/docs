# Delegating ZK Voting Power

The ZK token is used in the ZKsync governance system to provide voting power to participants through the process of delegation. Each ZK token holds 1 vote.

To activate the voting power of your ZK tokens, a token holder must delegate the voting power of their tokens to a ZKsync address. This address can be your own or a third-party. Once an address is delegated voting power, the controller of that address becomes a Delegate who is able to vote on governance proposals.

### How Delegation Works

* Delegating token voting power does not change the ownership of ZK tokens, but simply activates the voting power of ZK tokens and provides that voting power to an address chosen by the token holder.
* Delegation can be changed at any time by the token holder on [delegate.zknation.io](http://delegate.zknation.io/). Once token voting power is delegated, the delegation will persist until it is changed or the tokens are sold or transferred to a different address.
* Delegation cannot be split across multiple addresses. Once delegated, all voting power held in one wallet is delegated to a single address.
* ZK token voting power can only be delegated by the wallet owner. Tokens held within wallets on centralized exchanges cannot be delegated.
* Delegates who create a profile before Saturday June 15th at 11:59pm UTC will be eligible for consideration to be included in the ZK token claim flow.

### Why Delegating is Important

Delegation activates ZK token voting power. If an ecosystem requires an active Delegate base to meet quorum and approve governance proposals.

Through delegation, it is possible for someone who does not own any ZK tokens to hold voting power without acquiring ZK tokens directly. This increases participation in ZKsync governance.

If you are are interested in participating as a Delegate, visit [Getting Started as a ZKsync Delegate](https://forum.zknation.io/t/getting-started-as-a-zksync-delegate/104) for more information.

### Delegating through Governance Portals

* Visit [vote.zknation.io](https://delegate.zknation.io/dao)
* Connect your wallet & sign in if prompted
* Check you are on the ZKsync Era Mainnet network
* Select the "Delegate" button on the right-hand side of the screen
* Follow the prompts to select a Delegate, or self-delegate
* If delegating to yourself, sign the transaction to execute self-delegation
* If delegation to another address, enter the address and sign the transaction to execut delegation

### Delegating through Safe UI

* Login to your [Safe wallet](https://app.safe.global/welcome/accounts) and select "New transaction" in the top left corner.
* Select "Transaction Builder"&#x20;
* Enter the ZK token contract. All governance contracts can be found on the [ZKsync Governance Cotnract Addresses](../zk-nation/zksync-governance-contract-addresses.md) page. Once the address is entered, the ABI should load automatically.&#x20;
* Scroll down the page and change the _Contract Method Selector_ input. Change it to `delegate`
* Enter the address of the Delegate you would like to delegate to (yourself or another Delegate)
* Select “Add new transaction”
* Select “Create branch” in top right and follow the instructions in the Safe UI to review and execute the transaction

> For more details on how to delegate your voting power on Tally, [see this guide.](https://docs.tally.xyz/knowledge-base/delegations-on-tally/delegating-voting-power)
