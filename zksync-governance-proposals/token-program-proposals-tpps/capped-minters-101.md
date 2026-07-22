# Capped Minters 101

### What are Capped Minters?

Capped minters are unique smart contracts of the ZKsync ecosystem that allow for “just-in-time minting.” Each capped minter is assigned a maximum number of tokens, known as the “cap,” which is allowed to be minted. Those with the minter role of a capped minter can mint tokens from that supply whenever they choose to, up to the maximum specified. [Learn more about how Capped Minters](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps#what-is-a-capped-minter) are used in ZKsync token governance.

### ZK Capped Minter V3

The current version of the capped minter contract is the [ZKCappedMinterV3](https://github.com/zksync-association/zkminters/blob/main/src/ZkCappedMinterV3.sol). The ZK Capped Minter V3 expands the limited functionality of V2.

**ZK Capped Minter V3 Features Overview:**

* **Minting Cap:** Like V2, the ZK Capped Minter V3 enforces a strict upper limit on the total number of tokens that can be minted, ensuring controlled token allocations.
* **Multiple Minters:** Uses role-based permissions to manage minting rights, enabling the immutable admin to assign multiple minters for the capped minter.
* **Nested Minters:** As a result of the minter role, token programs can have hierarchies of nested capped minters. This is particularly useful for the creation of sub-programs, or agent-specific minting rights.
* **Transferable admin:** Unlike the V2, it is possible to transfer the admin role to a different address by the admin, enabling flexible deployment configuration & admin management
* **Updatable MINTABLE address:** Unlike the V2, the minting source of a program mechanic or capped minter can be updated if original source reaches the minting cap
* **Start and Expiration Dates:** Adds the ability to arbitrarily set a start and expiration time for a capped minter.
* **Pause and Close Operations:** Allows the admin to pause or fully cancel minting activities, providing a safeguard against unforeseen issues. The admin can also assign other addresses to have the power to pause.
* **Metadata:** Allows admin to set a custom metadata URI, allowing each minter to contained additional information related to connected token flows.
* **Events:** Emits onchain events for granting the minter role, minting, cancelling, setting metadata. New analytics and monitoring are possible.

### Deploying a Capped Minter

You can deploy a capped minter through a the [ZKCappedMinterV3 Factory](https://explorer.zksync.io/address/0xABF70d9a1fe52ca5e9339A6Ef76759614C1b5eE9#contract#write). You can find the source code for the V3 Factory [here](https://github.com/zksync-association/zkminters/blob/main/src/ZkCappedMinterV3.sol). The V3 Factory was created to make capped minter deployment more accessible.

> ℹ️ Testnet capped minter deployment can be done through the [Testnet\_ZkCappedMinterV3Factory](https://sepolia.explorer.zksync.io/address/0xABF70d9a1fe52ca5e9339A6Ef76759614C1b5eE9#contract%23write)

1. Go to the [CappedMinter V3 Factory](https://explorer.zksync.io/address/0xABF70d9a1fe52ca5e9339A6Ef76759614C1b5eE9#contract%23write)
2. Select “Contract” and “Write”
3. Toggle down "1. createMinter"

<figure><img src="../../.gitbook/assets/Screenshot 2026-03-09 at 16.01.02.png" alt=""><figcaption></figcaption></figure>

3. Connect your wallet
4.  Specify the parameters for the capped minter V3 being deployed:

    * **Mintable Token Address (`_mintable`):** The address of the token contract that will be minted from.
    * **Administrator Address (`_admin`):** The address granted administrative privileges, including the ability to assign the MINTER role.
    * **Minting Cap (`_cap`):** The maximum number of tokens that can be minted by this contract. This input is in uint256, meaning it requires 18 decimals. For example, if the cap is meant to be 1,000,000 ZK, it would be entered as 1000000000000000000000000.
    * **Start Time (`_startTime`):** The seconds timestamp from which minting is permitted. This input is in uint48 (i.e. epoch time). Use an epoch time converter to get the correct input for the start time desired. Please note that the start time has to be some time in the future from the moment of deployment.&#x20;
    * **Expiration Time (`_expirationTime`):** The seconds timestamp after which minting is no longer allowed. This input is in uint48 (i.e. epoch time). Use an epoch time converter to get the correct input for the end time desired. Please note that any child capped minters will expire on the specified end date of a parent capped minter.&#x20;
    * **saltNonce:** arbitrary value that helps define the deployed contract’s address.

    > Please note that these parameters cannot be updated after the contract has been deployed.&#x20;

<figure><img src="../../.gitbook/assets/Screenshot 2026-03-09 at 16.01.41.png" alt=""><figcaption></figcaption></figure>

**Where to find capped minter address after deployed:** After the transaction has been signed to create the capped minter, a hash should appear under the deploy button. Take note of the hash and go to the "Events" tab

### Verifying a Capped Minter

#### **Verifying in Command Line**

1. Set your working directory: Please note the input below is an EXAMPLE - customize as needed. This is where you will copy the contracts and build the folder system for the code.

```bash
cd Documents/Dev/

```

2. Clone the repo where governance contracts are managed

```bash
git clone <https://github.com/zksync-association/zk-governance.git>

```

3. (Optional) Install Hardhat ([see npm docs](https://docs.npmjs.com/cli/v8/configuring-npm/install))

```css
npm install --save-dev hardhat
npm install --save-dev typescript

```

4. Change directory to L2 governance contract working directory

```bash
cd l2-contracts/

```

5. Set default network
   1. // Change default network to zkSyncEra
   2. // (IF TESTNET) Change default network to zkSyncTestnet

```lua
nano hardhat.config.ts

```

6. Compile contracts

```python
npx hardhat compile

```

7. Verify Contract
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

_Example from the_ [_TPP-6_](https://vote.zknation.io/dao/proposal/38542076628472360665761284306860773162167153028104855759973536253827423667325?govId=eip155:324:0xb83FF6501214ddF40C91C9565d095400f3F45746) _capped minter._

### Nested Capped Minters (Parent / Child)

It is possible to nest “child” capped minters under a “parent” capped minter. While a parent capped minter’s target to mint from will always be the ZK token contract, a child’s target to mint from will be the parent (or a mod linked to the parent).

<figure><img src="../../.gitbook/assets/Parent_Child diagram.png" alt=""><figcaption></figcaption></figure>

#### **Grant minter role on deployed capped minters**

**Parent Capped Minters:** As only the admin of a contract can grant the minter role to another address, and the Token Governor Timelock (controlled by Token Assembly) is the admin of the ZK token contract, the minter role from the ZK token contract to any parent capped minter needs to be granted via governance proposal. Please see [Token Program Proposals (TPPs)](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps) to learn more about submitting a TPP. &#x20;

**Child Capped Minters & Mods:** The admin of each capped minter (that is not the Token Timelock) is able to grant the minter role on a capped minter without needing Token Assembly approval (e.g. on child capped minters/minter mods you are the admin of). There is no limit to how many addresses can have the minter role on a given minter contract. It is recommended that all minter roles are assigned in a mechanic before a proposal is submitted onchain for testing purposes and to ensure the smooth launch of a program.&#x20;

Follow these steps in order to grant the minter role on child minters or mods:

**Through Era Block Explorer:**

* Open the contract you want to grant the role from in the [Era block explorer](https://explorer.zksync.io/)
* Go to “Contract” > “Read”
* Select “MINTER ROLE” > query, copy the role address
* Go to “Write” tab > select “grantRole”, paste minter role address into “role” field
* Copy address you want to grant the role to in the “account” field
* Select “Write”

**Through Safe:**

* Make sure you are in the Safe account that is the admin of the capped minter you are granting the minter role from.
* Select “New Transaction” > Custom
* Enter the address of the Capped minter you are granting the minter role from
* **ABI:** If the ABI does not automatically show up, go to the capped minter address on the [Era block explorer](https://explorer.zksync.io/), go to “Contract”, scroll down to the bottom to find the “Contract ABI” field, copy & paste into ABI section on Safe
* **Action:** Section the action you want to execute (e.g. grantRole)
* **Enter Role Address:** To find the role adddress, open the contract you want to grant the role from in the Era block explorer, go to “Contract” > “Read”, select “MINTER ROLE” > query, copy the role address and paste into Safe
* **Enter Account Address:** Enter the address you want to grant the role to
* Follow instructions to propose/sign transaction to execute on the Safe interface.

### Common Role Addresses

There are two common roles that are assigned in standard token mechanics. These addresses can also be found directly in the contract functions of each minter contract. See [Reading a Capped Minter Contract](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps/capped-minters-101#reading-a-capped-minter-contract) section below.

<table><thead><tr><th width="118">Role</th><th width="336">Role Address</th><th>Role Action</th></tr></thead><tbody><tr><td>Minter Role</td><td>0x9f2df0fed2c77648de5860a4cc508cd0818c85b8b8a1ab4ceeef8d981c8956a6</td><td>Addresses granted this role will be able to mint from a given minter contract.</td></tr><tr><td>Pauser Role</td><td>0x65d7a28e3265b37a6474929f336521b332c1681b933f6cb9f3376673440d862a</td><td>Addresses with this role will be able to pause minting from a given minter contract. <br><br>This role is commonly assigned to the ZKsync Security Council for extra oversight on Token Programs.</td></tr></tbody></table>

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

**Verify child capped minter or minter mod has minter role on parent capped minter**

1. Open the Parent Capped Minter contract on the [Era Block Explorer](https://explorer.zksync.io/)
2. Go to Contract > Read as Proxy
3. Toggle down the hasRole parameter
4. Enter the MINTER\_ROLE address (query from above)
5. Enter address of the child capped minter
6. Select “Query”

If the query returns true, the child capped minter has the minter role on the parent capped minter and is able to mint up to it’s specified cap. If it returns false, it means the child capped minter does not have the minter role, and no tokens can be minted from that capped minter.

<figure><img src="../../.gitbook/assets/Screenshot 2025-08-29 at 16.57.44.png" alt=""><figcaption></figcaption></figure>

### Minting from a Capped Minter

> &#x20;ℹ️ Please note that only users assigned the minter role are able to mint from a capped minter. The Admin of a capped minter can assign the minter role on a give capped minter.

#### Minting ZK from Era Block Explorer

1. Enter the capped minter address you want to mint from in the [Era Block Explorer](https://explorer.zksync.io/)
2. Go to “Contract”, then “Write”
3. Connect the wallet that has the minter role
4. Toggle down the “mint” parameter
5. Enter address of where you want the ZK minted to in “\_to (address)”:
6. Enter the amount ZK in “amount (unit256)

> ℹ️ We recommend doing a test mint for a small portion of the full cap to the target address before minting the full cap.

7. Select “write”
8. Verify that the minted ZK was received by target address

#### Mint Tokens through Safe UI

1. Login to the SC Ops multisig [Safe wallet](https://app.safe.global/welcome/accounts) and select "New transaction" in the top left corner
2. Select “Transaction Builder”
3. Enter the capped minter contract address: (the ABI should automatically load)
4. Scroll down to “Contract Method Selector” and select “mint”
5. &#x20;Enter address of where you want the ZK minted to in “\_to (address)”:
6. Enter the amount ZK in “amount (unit256)

> ℹ️ We recommend doing a test mint for a small portion of the full cap to the target address before minting the full cap.

7. Select “Add new transaction”
8. Select “Create branch” in top right and follow the instructions in the Safe UI to review and execute the transaction
9. Verify that the minted ZK was received by target address
