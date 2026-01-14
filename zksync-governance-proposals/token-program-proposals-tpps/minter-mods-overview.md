# Minter Mods Overview

### What are Minter Mods?

Minter Modifiers, or “Minter Mods,” are additional contracts that can be deployed and connected to a [Capped Minter V2](https://docs.zknation.io/zksync-governance-proposals/token-program-proposals-tpps/capped-minters-101). Each Minter Mod is a separate contract that implements specific minting rules or restrictions, and they all follow a consistent interface (ZkMinterV1) that allows them to be composed together. These mods can be chained together in any order, with each one acting as a gatekeeper that must approved before the mint request reaches the CappedMinterV2.

The four current Minter Mods are the Rate Limiter Mod, Delay Mod, Eligibility Mod and Trigger Mod. Read more about each below.

### Why use Minter Mods?

Capped minters combined with Minter Mods provide the infrastructure to enforce custom minting and distribution rules, removing intermediary minted token custody management and the burden of manual token distribution for a given program. As a result, treasury-less and autonomous token programs can be composed, custom to the needs of a given program.

The idea behind Minter Mods comes from the challenges of managing token programs through manual multisig coordination. Relying on program admins to sign and execute large volumes of transactions creates operational bottlenecks and places significant trust in those admins to distribute tokens as promised in onchain proposals. By introducing programmatic enforcement of minting and distribution rules, this trust requirement is removed. Instead, the community can transparently verify the rules and roles that govern token minting at any time.

### Minter Mod Toolkit

There are currently four audited Minter Mods in the ZKsync Minter Mod toolkit. Visit the [zkminters repo](https://github.com/zksync-association/zkminters/tree/main) for all Minter Mod code & audits.

#### Rate Limiter Mod

<table data-header-hidden><thead><tr><th width="165"></th><th></th></tr></thead><tbody><tr><td><strong>Sourcecode</strong></td><td><a href="https://github.com/zksync-association/zkminters/blob/main/src/ZkMinterRateLimiterV1.sol">https://github.com/zksync-association/zkminters/blob/main/src/ZkMinterRateLimiterV1.sol</a></td></tr><tr><td><strong>Audit</strong></td><td><a href="https://github.com/zksync-association/zkminters/blob/main/audits/ZKRateLimiterReview_final_with_fixes.pdf">https://github.com/zksync-association/zkminters/blob/main/audits/ZKRateLimiterReview_final_with_fixes.pdf</a></td></tr><tr><td><strong>Deployment Factory</strong></td><td><a href="https://explorer.zksync.io/address/0x6Cb59905FCEDA9f578a5fAC5867D0560f762Cb00#contract%23write">ZkMinterRateLimiterV1Factory</a></td></tr></tbody></table>

**Description:** Limits the rate at which tokens can be minted over a specified period of time (e.g. day, week, month). This enables Token Programs to be “self-serve” and adds a level of security by putting a cap on how much any party with minting rights can mint within a given time period.&#x20;

**Examples of use:**

* **Self-serve service provider payments**: Grant a program service provider minting rights on a capped minter with a cap of the full program payment with a rate limiter that limits their monthly minting amount to the agreed upon monthly rate.
* **Vesting Tool:** In a particular prize program, each prize capped minter has a rate limit on it to limit the amount a winner can mint in 1 day/week/month.
* **Price fluctuation protection**: Put a “global” rate limiter on a program parent capped minter (rather than on each child capped minter) to prevent the total amount minted from any children to not succeed a certain amount from the parent if price fluctuates dramatically during the program.

**How to deploy:** Use the [ZkMinterRateLimiterV1Factory](https://explorer.zksync.io/address/0x6Cb59905FCEDA9f578a5fAC5867D0560f762Cb00#contract%23write) to deploy a Rate Limiter mod. Please reach out to the ZKsync Governance Team for guidance on mechanic deployment.

> The admin of a Rate Limiter contract is able to update the \_mintRateLimit and \_mintRateLimitWindow variables after it has been deployed if needed.&#x20;

#### Delay Mod

<table data-header-hidden><thead><tr><th width="164.5"></th><th></th></tr></thead><tbody><tr><td><strong>Sourcecode</strong></td><td><a href="https://github.com/zksync-association/zkminters/blob/main/src/ZkMinterDelayV1.sol">https://github.com/zksync-association/zkminters/blob/main/src/ZkMinterDelayV1.sol</a></td></tr><tr><td><strong>Audit</strong></td><td><a href="https://github.com/zksync-association/zkminters/blob/main/audits/ZKMinterDelayModV1Review_final_with_fixes.pdf">https://github.com/zksync-association/zkminters/blob/main/audits/ZKMinterDelayModV1Review_final_with_fixes.pdf</a></td></tr><tr><td><strong>Deployment Factory</strong></td><td><a href="https://explorer.zksync.io/address/0x022cd302a2A0C7f78EC17341cAB911eCE3E7CCC5#contract%23write">ZkMinterDelayV1Factory</a></td></tr></tbody></table>

**Description:** Creates a time delay (veto window) between a mint request and mint execution on the linked capped minter. In practice, this enables Token Programs to be “self-serve” & allow for flexible minting allowance.

**Examples of use:**

* **Self-serve Payments:** A Token Program service provider has a service agreement to provide up to 100K ZK worth of services/month. Each month, the services provider can request to mint payment for work completed that month (e.g. up to 100K ZK) from the program capped minter (rather than SteerCo having to mint tokens & send to service provider.) If the service provider’s request is not aligned to monthly service agreement (e.g. request of 200K ZK), the SteerCo can simply deny the request (veto) within the specified delay window.
* **Optimistic Prize Claim:** Parties with minter role are able to claim a prize optimistically by requesting a mint. Only after veto / verification window will the mint request be available.

**How to deploy:** Use the [ZkMinterDelayV1Factory](https://explorer.zksync.io/address/0x022cd302a2A0C7f78EC17341cAB911eCE3E7CCC5#contract%23write) to deploy a Delay Mod. Please reach out to the ZKsync Governance Team for guidance on mechanic deployment.

#### Eligibility Mod

<table data-header-hidden><thead><tr><th width="165"></th><th></th></tr></thead><tbody><tr><td><strong>Sourcecode</strong></td><td><a href="https://github.com/zksync-association/zkminters/blob/main/src/ZkMinterERC1155EligibilityV1.sol">https://github.com/zksync-association/zkminters/blob/main/src/ZkMinterERC1155EligibilityV1.sol</a></td></tr><tr><td><strong>Audit</strong></td><td><a href="https://github.com/zksync-association/zkminters/blob/main/audits/ERC1155EligibilityMinterV1Review.pdf">https://github.com/zksync-association/zkminters/blob/main/audits/ERC1155EligibilityMinterV1Review.pdf</a></td></tr><tr><td><strong>Deployment Factory</strong></td><td>ZkMinterERC1155EligibilityV1Factory (pending)</td></tr></tbody></table>

**Description:** Limits who can mint from a specific capped minter based on holding a specific ERC1155-based token. Anyone holding a specific ERC1155 will be able to mint from a linked capped minter. This mod could be copied and adapted to work with other ERCs.

**Examples of use:**

* **Self-claiming rewards:** In a self-claiming reward mechanic, only participants holding a specific ERC-1155 is able to mint from a specific capped minter.
* **Multiple Unknown Minters:** More than one party is expected to need the minter role on a capped minter that may be unknown at the time of launch. Assign the minter role to an ERC1155 (e.g. a Hat) so that anyone with that Hat (which can be distributed later), has minting rights on a give capped minter.

**How to deploy:** Use the **ZkMinterERC1155EligibilityV1Factory** (pending) to deploy an Eligibility Mod. Please reach out to the ZKsync Governance Team for guidance on mechanic deployment.

#### Trigger Mod

<table><thead><tr><th width="164.5"></th><th></th></tr></thead><tbody><tr><td><strong>Sourcecode</strong></td><td>Pending</td></tr><tr><td><strong>Audit</strong></td><td>Pending</td></tr><tr><td><strong>Deployment Factory</strong></td><td>Pending</td></tr></tbody></table>

**Description:** Enables creation of separate “mint” & “trigger” functions on a capped minter, and the assignment of an immutable target address to a capped minter. The trigger mod allows one to immediately execute multiple function calls - all in one atomic transaction.

**Examples of use:**

* **Mint to contract:** A vendor needs to be paid through a streaming contract (e.g. Drips, Hedgy). The trigger contract can be used to autonomously mint and send the minted tokens to the given streaming contract, removing the risk of custody management of minted tokens from the program admin.
* **USD Denomination:** A vendor’s service fee is denominated in USD. The trigger mod contract can automate the ZK <> USDC conversion calculation, mint and send action on a specified regular basis (e.g. monthly).
* **Operational Security:** The trigger mod allows the admin to set an immutable target address, meaning regardless of who or what triggers the mint, it will always be minted to the same target address.

**How to deploy:** Use the **Trigger Mod Factory** (pending) to deploy a Trigger Mod. Please reach out to the ZKsync Governance Team for guidance on mechanic deployment.

### Build A New Minter Mod

Every project has unique minting requirements that may not be supported by the current set of Minter Mods. We invite others to play around with Minter Mods Learn more about how to [deploy your own Minter Mod here](https://github.com/zksync-association/zkminters/tree/main#building-a-new-minter-mod)!

Have an idea for a new minter mod or example of how they could be used? Post it in the [Token Mechanics category](https://forum.zknation.io/c/token-mechanics/26) on the forum.
