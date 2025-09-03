# Capped Minters 101

### What are Capped Minters?

Capped minters are unique smart contracts of the ZKsync ecosystem that allow for “just-in-time minting.” Each capped minter is assigned a maximum number of tokens, known as the “cap,” which is allowed to be minted. Those with the minter role of a capped minter can mint tokens from that supply whenever they choose to, up to the maximum specified. [Learn more about how Capped Minters](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps#what-is-a-capped-minter) are used in ZKsync token governance.

### ZK Capped Minter V2

The current version of the capped minter contract is the [ZKCappedMinterV2](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkCappedMinterV2.sol). The ZK Capped Minter V2 expands the limited functionality of V1, where the creator could assign a token, admin, and cap.

**ZK Capped Minter V2 Features Overview:**

* **Minting Cap:** Like V1, the ZK Capped Minter V2 enforces a strict upper limit on the total number of tokens that can be minted, ensuring controlled token allocations.
* **Multiple Minters:** Uses role-based permissions to manage minting rights, enabling the immutable admin to assign multiple minters for the capped minter.
* **Nested Minters:** As a result of the minter role, token programs can have hierarchies of nested capped minters. This is particularly useful for the creation of sub-programs, or agent-specific minting rights.
* **Start and Expiration Dates:** Adds the ability to arbitrarily set a start and expiration time for a capped minter.
* **Pause and Cancel Operations:** Allows the admin to pause or fully cancel minting activities, providing a safeguard against unforeseen issues. The admin can also assign other addresses to have the power to pause.
* **Metadata:** Allows admin to set a custom metadata URI, allowing each minter to contained additional information related to connected token flows.
* **Events:** Emits onchain events for granting the minter role, minting, cancelling, setting metadata. New analytics and monitoring are possible.

### Deploying a Capped Minter

You can deploy a capped minter through a the [ZKCappedMinterV2 Factory](https://explorer.zksync.io/address/0x0400E6bc22B68686Fb197E91f66E199C6b0DDD6a#contract#contract-info). You can find the source code for the V2 Factory [here](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkCappedMinterV2Factory.sol). The V2 Factory was created to make capped minter deployment more accessible.

1. Go to the [CappedMinter V2 Factory](https://explorer.zksync.io/address/0x0400E6bc22B68686Fb197E91f66E199C6b0DDD6a#contract#contract-info)
2. Select “Contract” and “Write”

![Screenshot 2025-03-19 at 10.30.21](https://forum.zknation.io/uploads/db7785/optimized/1X/dc41a0dd33d0ceaffe92081358c0b8406ad34c6a_2_690x407.png)

3. Connect your wallet
4. Specificy the parameters for the capped minter V2 being deployed:
   * **Mintable Token Address (`_mintable`):** The address of the token contract that will be minted from.
   * **Administrator Address (`_admin`):** The address granted administrative privileges, including the ability to assign the MINTER role.
   * **Minting Cap (`_cap`):** The maximum number of tokens that can be minted by this contract.
   * **Start Time (`_startTime`):** The seconds timestamp from which minting is permitted.
   * **Expiration Time (`_expirationTime`):** The seconds timestamp after which minting is no longer allowed. Please note that any child capped minters will expire on the specified end date of a parent capped minter.
   * **saltNonce:** arbitrary value that helps define the deployed contract’s address.

![Screenshot 2025-03-19 at 10.58.50](https://forum.zknation.io/uploads/db7785/optimized/1X/8b46925e76e4573a035d64c0080c14f8d129b058_2_679x500.png)

### Verifying a Capped Minter

#### **Verifying in Command Line**

1. Set your working directory: Please note the input below is an EXAMPLE - customize as needed. This is where you will copy the contracts and build the folder system for the code.

```bash
cd Documents/Dev/

```

1. Clone the repo where governance contracts are managed

```bash
git clone <https://github.com/zksync-association/zk-governance.git>

```

1. (Optional) Install Hardhat ([see npm docs](https://docs.npmjs.com/cli/v8/configuring-npm/install))

```css
npm install --save-dev hardhat
npm install --save-dev typescript

```

1. Change directory to L2 governance contract working directory

```bash
cd l2-contracts/

```

1. Set default network
   1. // Change default network to zkSyncEra
   2. // (IF TESTNET) Change default network to zkSyncTestnet

```lua
nano hardhat.config.ts

```

1. Compile contracts

```python
npx hardhat compile

```

1. Verify Contract
   1. npx hardhat verify \[contract address] \[token] \[admin] \[cap] \[starttime] \[expirationtime]
   2. Change your parameters as needed

EXAMPLE:

```
npx hardhat verify 0x721b6d77a58FaaF540bE49F28D668a46214Ba44c 0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E 0x77CC0A0582475bfD74CD838610e817d05c181E11 8301475000000000000000000 1736899200 1752537600

```

### Reading a Capped Minter Contract

In order to read the parameters of an already deployed capped minter contract, simply paste the address in the [ZKsync Era Block Explorer](https://explorer.zksync.io/), go to “Contract”, and the “Read”. There, you will find the following parameters.

<figure><img src="../../.gitbook/assets/Screenshot 2025-08-21 at 15.47.40.png" alt=""><figcaption></figcaption></figure>

1. CAP: Query this parameter to see the immutable cap on a given capped minter
2. DEFAULT\_ADMIN\_ROLE: Query this parameter to get the default admin role address
3. EXPIRATION\_TIME: Query this parameter to see the end (expiration) date of a capped minter
4. MINTABLE: Query this parameter to get the address of the token being minter (ZK)
5. MINTER\_ROLE: Query this parameter to get the minter role address for this capped minter
6. PAUSER\_ROLE: Query this parameter to get the pauser role address for this capped minter
7. START\_TIME: Query this parameter to see the start (activation) date of a capped minter
8. closed: Query this parameter to check if the minter is closed
9. getRoleAdmin: Query this parameter to see if a role is an admin of another role on the capped minter
10. hasRole: Query this parameter to verify if a specific address has a certain role
11. metadataURI: Query this parameter to get a URI for capped minter metadata
12. minted: Query this parameter to see how much ZK has been minted from the CAP
13. paused: Query this parameter to see if the capped minter contract has been pause (true = paused, false = not paused)
14. supportsinterface: Query this parameter by adding an interface ID to check if an interface is supported with the contract

### Confirming the Minter Role on a Capped Minter

Minting rights are represented by the minter role. The minter role is granted and revoked by passing a Token Program Proposal (TPP). To verify if a capped minter has the minter role or not, following the steps below.

**Verify Parent Capped Minter has minter role on ZK token contract**

1. Open the [ZK token contract](https://sepolia.explorer.zksync.io/address/0x06eb75609e3c8daebe26e479e7232edeb25bc1c2#contract) on the Era Block Explorer
2. Go to Contract > Read
3. Toggle down the hasRole parameter
4. Enter the MINTER\_ROLE address (query from above)
5. Enter address of the capped minter
6. Select “Query”

If the query returns true, the capped minter has the minter role on the ZK token contract and is able to mint up to it’s specified cap. If it returns false, it means the capped minter does not have the minter role, and no tokens can be minted from that capped minter.

<figure><img src="../../.gitbook/assets/Screenshot 2025-08-29 at 16.57.44.png" alt=""><figcaption></figcaption></figure>

_Example from the_ [_TPP-6_](https://vote.zknation.io/dao/proposal/38542076628472360665761284306860773162167153028104855759973536253827423667325?govId=eip155:324:0xb83FF6501214ddF40C91C9565d095400f3F45746) _capped minter._

### Nested Capped Minters (Parent / Child)

It is possible to nest “child” capped minters under a “parent” capped minter. While a parent capped minter’s target to mint from will always be the ZK token contract, a child’s target to mint from will be the parent (or a mod linked to the parent).

<figure><img src="../../.gitbook/assets/Parent_Child diagram.png" alt=""><figcaption></figcaption></figure>

#### **Verify Child Capped Minter has minter role on parent capped minter**

1. Open the Parent Capped Minter contract on the [Era Block Explorer](https://explorer.zksync.io/)
2. Go to Contract > Read as Proxy
3. Toggle down the hasRole parameter
4. Enter the MINTER\_ROLE address (query from above)
5. Enter address of the child capped minter
6. Select “Query”

If the query returns true, the child capped minter has the minter role on the parent capped minter and is able to mint up to it’s specified cap. If it returns false, it means the child capped minter does not have the minter role, and no tokens can be minted from that capped minter.

### Minting from a Capped Minter

> &#x20;ℹ️ Please note that only users assigned the minter role are able to mint from a capped minter. The Admin of a capped minter can assign the minter role on a give capped minter.

#### Minting ZK from Era Block Explorer

* Enter the capped minter address you want to mint from in the [Era Block Explorer](https://explorer.zksync.io/)
* Go to “Contract”, then “Write”
* Connect the wallet that has the minter role
* Toggle down the “mint” parameter
* Enter address of where you want the ZK minted to in “\_to (address)”:
*   Enter the amount ZK in “amount (unit256)

    > ℹ️ We recommend doing a test mint for a small portion of the full cap to the target address before minting the full cap.
* Select “write”
* Verify that the minted ZK was received by target address

#### Mint Tokens through Safe UI

* Login to the SC Ops multisig [Safe wallet](https://app.safe.global/welcome/accounts) and select "New transaction" in the top left corner
* Select “Transaction Builder”
* Enter the capped minter contract address: (the ABI should automatically load)
* Scroll down to “Contract Method Selector” and select “mint”
* Enter address of where you want the ZK minted to in “\_to (address)”:
*   Enter the amount ZK in “amount (unit256)

    > ℹ️ We recommend doing a test mint for a small portion of the full cap to the target address before minting the full cap.
* Select “Add new transaction”
* Select “Create branch” in top right and follow the instructions in the Safe UI to review and execute the transaction
* Verify that the minted ZK was received by target address
