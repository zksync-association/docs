# Voting on Proposals

Delegates who have been delegated ZK token voting power can vote on ZKsync governance proposals. See the different ways Delegates can vote on proposals below. [Click here](https://docs.zknation.io/voting-and-delegation/zk-token-delegation) to learn more about delegation.

### Voting through Governance Portals

Delegates can interact with ZKsync contracts through specialized website applications called governance portals. Currently, there are two primary governance portals connected to ZKsync governance contracts:

1. **Tally:** The ZKsync Tally Governance Portal is owned and managed by the ZKsync Association. You can access the portal at [vote.zknation.io](http://vote.zknation.io). Follow [these steps](https://docs.tally.xyz/user-guides/using-governor-with-gnosis-safe/voting-with-a-gnosis-safe) to vote with a multisig on Tally.
2. **Boardroom:** Boardroom was recently deprecated. The ZKsync Association is running an RFP process to replace Boardroom as a secondary governance interface.

### Voting through the ZKsync Era Block Explorer

Besides governance portals, anyone can interact with ZKsync governance contracts on the [ZKsync Era Block Explorer](http://explorer.zksync.io). Follow these steps to vote:

#### Step 1: Select the Right Governor

Navigate to the right governor contract by pasting the relevant governor contract address into the ZKsync Era Block Explorer search bar.

* For Protocol Upgrade Proposals (or “ZKsync Improvement Proposals”), use the Protocol Governor address.
* For Token Program Proposals, use the Token Governor address.
* For Governance Advisory Proposals, use the GovOps Governor address.

<figure><img src="../.gitbook/assets/voting image 1.png" alt=""><figcaption></figcaption></figure>

#### Step 2: View Governor Contract

* Navigate to the “Contract” tab
* Select “Write”

<figure><img src="../.gitbook/assets/voting image 2.png" alt=""><figcaption></figcaption></figure>

#### Step 3: Find the Right Proposal

* Identify the proposal ID, for example on Tally

<figure><img src="../.gitbook/assets/voting image 3.png" alt=""><figcaption></figcaption></figure>

#### Step 4: Prepare Vote

* Go back to the Governor Contract / Write as Proxy
* Go to “castVote” function OR “castVoteWithReason”
  * Paste the Proposal ID
  * Vote FOR the proposal by assigning a value of `1` OR
  * Vote AGAINST the proposal by assigning a value of `0` OR
  * Vote ABSTAIN the proposal by assigning a value of ‘2’
* If you called the function `castVoteWithReason` add a string of text with your comment

<figure><img src="../.gitbook/assets/voting image 4.png" alt=""><figcaption></figcaption></figure>

#### Step 5: Complete Vote

* Make sure to “Connect Wallet”
* Then, click on “Write”
* Complete the transaction

### Voting through Safe UI

If you are voting with a Safe multisig, in addition to voting through [vote.zknation.io](http://vote.zknation.io), you are able to cast your vote through the Safe UI. Follow these steps:&#x20;

#### Step 1: Login to your Safe Wallet

Login to your [Safe wallet](https://app.safe.global/welcome/accounts) and select "New transaction" in the top left corner.

<figure><img src="../.gitbook/assets/Screenshot 2025-07-21 at 15.04.24.png" alt=""><figcaption></figcaption></figure>

#### Step 2: Select the right Governor

Enter the right governor contract by pasting the relevant governor contract address into the ZKsync Era Block Explorer search bar. All governor contracts can be found on the [ZKsync Governance Cotnract Addresses](../zk-nation/zksync-governance-contract-addresses.md) page.&#x20;

* For Protocol Upgrade Proposals (or “ZKsync Improvement Proposals”), use the Protocol Governor address.
* For Token Program Proposals, use the Token Governor address.
* For Governance Advisory Proposals, use the GovOps Governor address.

Once the address is entered, the ABI should load automatically.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-07-21 at 15.10.39.png" alt=""><figcaption></figcaption></figure>

#### Step 3: Select Action

* Scroll down the page and change the _Contract Method Selector_ input. Change it to `castVote` or `castVoteWithReason` if you prefer to leave a note on why you voted a certain way. &#x20;

<figure><img src="../.gitbook/assets/Screenshot 2025-07-21 at 15.13.13.png" alt=""><figcaption></figcaption></figure>

#### Step 4: Find the right proposal

* Identify the correct proposal ID, for example on Tally

<figure><img src="../.gitbook/assets/voting image 3.png" alt=""><figcaption></figcaption></figure>

#### Step 5: Prepare Vote

* Fill out the remaining parameters:
  * Paste the Proposal ID
  * In the _Support_ input, enter one of the following:&#x20;
    * Vote FOR the proposal by assigning a value of `1` OR
    * Vote AGAINST the proposal by assigning a value of `0` OR
    * Vote ABSTAIN the proposal by assigning a value of `2`
* If you called the function `castVoteWithReason` add a string of text with your comment

#### Step 6: Complete Vote

* Select "New Transaction" at the bottom of the page
* Select "Create Batch" in the top right corner
* Follow the instructions in the Safe UI to review and execute the transaction

<figure><img src="../.gitbook/assets/Screenshot 2025-07-21 at 15.13.38.png" alt=""><figcaption></figcaption></figure>

