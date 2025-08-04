# ZKsync Governance Contract Addresses

## **ZKsync Governance System: Production Contracts**

### L2 Contracts

* Token:
  * ZK Token: [0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E](https://explorer.zksync.io/address/0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E)
* ZkProtocolGovernor
  * Governor: [0x76705327e682F2d96943280D99464Ab61219e34f](https://explorer.zksync.io/address/0x76705327e682F2d96943280D99464Ab61219e34f)
  * Timelock: [0x085b8B6407f150D62adB1EF926F7f304600ec714](https://explorer.zksync.io/address/0x085b8B6407f150D62adB1EF926F7f304600ec714)
* ZkTokenGovernor
  * Governor: [0xb83FF6501214ddF40C91C9565d095400f3F45746](https://explorer.zksync.io/address/0xb83FF6501214ddF40C91C9565d095400f3F45746)
  * Timelock: [0xe5d21A9179CA2E1F0F327d598D464CcF60d89c3d](https://explorer.zksync.io/address/0xe5d21A9179CA2E1F0F327d598D464CcF60d89c3d)
* ZkGovOpsGovernor
  * Governor: [0xEEEa739a8b6fB1b8f703E23C9Be03CeeA643b160](https://explorer.zksync.io/address/0xEEEa739a8b6fB1b8f703E23C9Be03CeeA643b160)
  * Timelock: [0xC9E442574958f96C026DeF9a50C3236cab17428a](https://explorer.zksync.io/address/0xC9E442574958f96C026DeF9a50C3236cab17428a)
* Capped Minter Deployment
  * [ZkCappedMinterV2.sol](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkCappedMinterV2.sol)
  * [ZkCappedMinterV2Factory.sol](https://github.com/zksync-association/zk-governance/blob/master/l2-contracts/src/ZkCappedMinterV2Factory.sol)
  * ZkCappedMinterV2Factory: [0x0400E6bc22B68686Fb197E91f66E199C6b0DDD6a](https://explorer.zksync.io/address/0x0400E6bc22B68686Fb197E91f66E199C6b0DDD6a#contract#contract-info)
* Active ZK Capped Minters
  * [0x66fd4fc8fa52c9bec2aba368047a0b27e24ecfe4](https://explorer.zksync.io/address/0x66fd4fc8fa52c9bec2aba368047a0b27e24ecfe4) (Initial Merkle Distributor for ZK Airdrop)
  * [0xb294F411cB52c7C6B6c0B0b61DBDf398a8b0725d](https://explorer.zksync.io/address/0xb294F411cB52c7C6B6c0B0b61DBDf398a8b0725d) (Second Distributor for ZK Airdrop)
  * [0xf29d698e74ef1904bcfdb20ed38f9f3ef0a89e5b](https://explorer.zksync.io/address/0xf29d698e74ef1904bcfdb20ed38f9f3ef0a89e5b) (Third Distributor for ZK Airdrop)
  * [0xa97fbc75ccbc7d4353c4d2676ed18cd0c5aaf7e6](https://explorer.zksync.io/address/0xa97fbc75ccbc7d4353c4d2676ed18cd0c5aaf7e6) (Matter Labs ZK Token Allocation)
  * [0xd78dc27d4db8f428c67f542216a2b23663838405](https://explorer.zksync.io/address/0xd78dc27d4db8f428c67f542216a2b23663838405) (ZKsync Foundation ZK Token Allocation)
  * [0x21b27952f8621f54f3cb652630e122ec81dd2dc1](https://explorer.zksync.io/address/0x21b27952f8621f54f3cb652630e122ec81dd2dc1) (Guardians ZK Token Allocation)
  * [0x0ad50686c159040e57ddce137db0b63c67473450](https://explorer.zksync.io/address/0x0ad50686c159040e57ddce137db0b63c67473450) (Security Council ZK Token Allocation)
  * [0x0681e3808a0aa12004fb815ebb4515dc823cfbb4](https://explorer.zksync.io/address/0x0681e3808a0aa12004fb815ebb4515dc823cfbb4) (ZKsync Association ZK Token Allocation)

### L1 Contracts

* Protocol Upgrade Handler address: [0xE30Dca3047B37dc7d88849dE4A4Dc07937ad5Ab3](https://etherscan.io/address/0xE30Dca3047B37dc7d88849dE4A4Dc07937ad5Ab3)
* Emergency Upgrade Board address: [0xECE8e30bFc92c2A8e11e6cb2e17B70868572E3f6](https://etherscan.io/address/0xECE8e30bFc92c2A8e11e6cb2e17B70868572E3f6)
* Guardians address: [0x600dA620Ab29F41ABC6596a15981e14cE58c86b8](https://etherscan.io/address/0x600dA620Ab29F41ABC6596a15981e14cE58c86b8)
* Security Council address: [0x66E4431266DC7E04E7d8b7FE9d2181253df7F410](https://etherscan.io/address/0x66E4431266DC7E04E7d8b7FE9d2181253df7F410)
* Foundation address: [0xbC1653bd3829dfEc575AfC3816D4899cd103B51c](https://etherscan.io/address/0xbC1653bd3829dfEc575AfC3816D4899cd103B51c)

### Depricated Production Contracts:

{% hint style="info" %}
As s result of how [ZIP-5](https://vote.zknation.io/dao/proposal/32477831455745537024214395992964479454779258818502397012096084176779102554510?govId=eip155:324:0x76705327e682F2d96943280D99464Ab61219e34f) was executed, certain contracts listed above were updated. The depricated contracts are listed below.&#x20;
{% endhint %}

ZkProtocolGovernor

* Timelock: [0x3701fB675bCd4A85eb11A2467628BBe193F6e6A8](https://explorer.zksync.io/address/0x3701fB675bCd4A85eb11A2467628BBe193F6e6A8)

ZkTokenGovernor

* Governor: [0x10560f8B7eE37571AD7E3702EEb12Bc422036E89](https://explorer.zksync.io/address/0x10560f8B7eE37571AD7E3702EEb12Bc422036E89)
* Timelock: [0x3E21c654B545Bf6236DC08236169DcF13dA4dDd6](https://explorer.zksync.io/address/0x3E21c654B545Bf6236DC08236169DcF13dA4dDd6)

ZkGovOpsGovernor

* Governor: [0x496869a7575A1f907D1C5B1eca28e4e9E382afAb](https://explorer.zksync.io/address/0x496869a7575A1f907D1C5B1eca28e4e9E382afAb)
* Timelock: [0xC3e970cB015B5FC36edDf293D2370ef5D00F7a19](https://explorer.zksync.io/address/0xC3e970cB015B5FC36edDf293D2370ef5D00F7a19)

L1 Contracts

* Protocol Upgrade Handler address: [0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897)
* Emergency Upgrade Board address: [0xdEFd1eDEE3E8c5965216bd59C866f7f5307C9b29](https://etherscan.io/address/0xdEFd1eDEE3E8c5965216bd59C866f7f5307C9b29)
* Guardians address: [0xD677e09324F8Bb3cC64F009973693f751c33A888](https://etherscan.io/address/0xD677e09324F8Bb3cC64F009973693f751c33A888)
* Security Council address: [0xBDFfCC71FE84020238F2990a6D2954e87355De0D](https://etherscan.io/address/0xBDFfCC71FE84020238F2990a6D2954e87355De0D)

## **ZKsync Governance System: Testnet Contracts**

### L2 Contracts

* Token:
  * ZK Token: [0x69e5DC39E2bCb1C17053d2A4ee7CAEAAc5D36f96](https://sepolia.explorer.zksync.io/address/0x69e5DC39E2bCb1C17053d2A4ee7CAEAAc5D36f96)
* ZkProtocolGovernor
  * Governor: [0x5a6862ee581b6cDb517D24f0a69237f9D900C23C](https://sepolia.explorer.zksync.io/address/0x5a6862ee581b6cDb517D24f0a69237f9D900C23C)
  * Timelock: [0xa0eD7885B408961430F89d797cD1cc87530D8fBe](https://sepolia.explorer.zksync.io/address/0xa0eD7885B408961430F89d797cD1cc87530D8fBe)
* ZkTokenGovernor
  * Governor: [0x98fF5B31bBa84f5Ad05a7635a436151F74aDa466](https://sepolia.explorer.zksync.io/address/0x98fF5B31bBa84f5Ad05a7635a436151F74aDa466)
  * Timelock: [0x0d9DD6964692a0027e1645902536E7A3b34AA1d7](https://sepolia.explorer.zksync.io/address/0x0d9DD6964692a0027e1645902536E7A3b34AA1d7)
* ZkGovOpsGovernor
  * Governor: [0x56f6379F945e95558069acb3E945ee3480025605](https://sepolia.explorer.zksync.io/address/0x56f6379F945e95558069acb3E945ee3480025605)
  * Timelock: [0x0569a17602Ef32B8aa2fdeC44DCD3F7109f96f91](https://sepolia.explorer.zksync.io/address/0x0569a17602Ef32B8aa2fdeC44DCD3F7109f96f91)
* Capped Minter Deployment
  * ZkCappedMinterV2Factory: [0x329CE320a0Ef03F8c0E01195604b5ef7D3Fb150E](https://sepolia.explorer.zksync.io/address/0x329CE320a0Ef03F8c0E01195604b5ef7D3Fb150E#contract#write)

### L1 Contracts

* Protocol Upgrade Handler proxy address: [0xe3a615778aeEC76df1B368948a1D1614497Db858](https://sepolia.etherscan.io/address/0xe3a615778aeEC76df1B368948a1D1614497Db858)
* Emergency Upgrade Board address: [0x0B2b3D1d87933C5009C49EffBAe279cdF39c6C96](https://sepolia.etherscan.io/address/0x0B2b3D1d87933C5009C49EffBAe279cdF39c6C96)
* Guardians address: [0x3A8Ac6A7a4A026F42f805B40bB992edF01654595](https://sepolia.etherscan.io/address/0x3A8Ac6A7a4A026F42f805B40bB992edF01654595)
* Security Council address: [0x25Ab0397DA109A50C8921A1d4a034e0973602469](https://sepolia.etherscan.io/address/0x25Ab0397DA109A50C8921A1d4a034e0973602469)
* Foundation address: [0x46d3c220de912100DE9Ee5052511ad5FCb2C190b](https://sepolia.etherscan.io/address/0x46d3c220de912100DE9Ee5052511ad5FCb2C190b)

### Depricated Testnet Contracts:

{% hint style="info" %}
As s result of how [ZIP-5](https://vote.zknation.io/dao/proposal/32477831455745537024214395992964479454779258818502397012096084176779102554510?govId=eip155:324:0x76705327e682F2d96943280D99464Ab61219e34f) was executed, certain contracts listed above were updated. The depricated contracts are listed below.&#x20;
{% endhint %}

ZkProtocolGovernor

* Timelock: [0x59EF1efe5e031b56a987603cD9CBAfBA48Dd1833](https://sepolia.explorer.zksync.io/address/0x59EF1efe5e031b56a987603cD9CBAfBA48Dd1833)

L1 Contracts

* Protocol Upgrade Handler address: [0x9B956d242e6806044877C7C1B530D475E371d544](https://sepolia.etherscan.io/address/0x9B956d242e6806044877C7C1B530D475E371d544)
* Emergency Upgrade Board address: [0xfC4cf3248A8f5fbA7Fa6bD67a3BB43cfc7514e55](https://sepolia.etherscan.io/address/0xfC4cf3248A8f5fbA7Fa6bD67a3BB43cfc7514e55)
* Guardians address: [0xe95141dd86828D23c2aA8Ed518644Af5e4216D79](https://sepolia.etherscan.io/address/0xe95141dd86828D23c2aA8Ed518644Af5e4216D79)
* Security Council address: [0x541E05fbe96895095E0f4b70865AbaC70cb12e0e](https://sepolia.etherscan.io/address/0x541E05fbe96895095E0f4b70865AbaC70cb12e0e)

## Ownership Transfer Sequence

1. A transfer of ownership of [L1SharedBridge](https://etherscan.io/address/0xd7f9f54194c633f36ccd5f3da84ad4a1c38cb2cb), [BridgeHub](https://etherscan.io/address/0x303a465b659cbb0ab36ee643ea362c509eeb5213), [StateTransitionManager](https://etherscan.io/address/0xc2ee6b6af7d616f6e27ce7f4a451aedc2b0f5f5c), [ValidatorTimelock](https://etherscan.io/address/0x5d8ba173dc6c3c90c8f7c04c9288bef5fdbad06e) from a centralized 4/7 multisig to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897) was proposed. [Transaction link](https://etherscan.io/tx/0x83d26938171003102f077922c8b32ddf01a3994f654aa1c684453fb2b36456a5).
2. [EmergencyUpgradeBoard](https://etherscan.io/address/0xdefd1edee3e8c5965216bd59c866f7f5307c9b29) accepted ownership of the contracts in the previous step by executing an emergency upgrade approved by the Security Council, Guardians, and the Foundation. [Transaction link](https://etherscan.io/tx/0x04252ef77e208a233dfe0e7a3c70a04c8c8e95364c6ec67e5dd4ca7299bad8cb).
3. Ownership of [ProxyAdmin](https://etherscan.io/address/0xC2a36181fB524a6bEfE639aFEd37A67e77d62cf1) was transferred to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897). [Transaction link](https://etherscan.io/tx/0x16775779a40b1f754fb8a4724f27f0a2065ed4d6e5862ea10ad9083d1f190d08).
4. Onwership of [Era L2 ProxyAdmin](https://era.zksync.network/address/0xdB1E46B448e68a5E35CB693a99D59f784aD115CC) was transferred to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897), aliased L2 address `0xA08b9912416E8aDc4D9C21Fae1415d3318A129A8`. [Transaction link](https://explorer.zksync.io/tx/0xcb7c4f89ff61c472e6fdb89500518c4ebb7b6b52ee47a27fe673b680734a7935).
5. Ownership of [Era UpgradeableBeacon](https://explorer.zksync.io/address/0x1Eb710030273e529A6aD7E1e14D4e601765Ba3c6) was transferred to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897), aliased L2 address `0xA08b9912416E8aDc4D9C21Fae1415d3318A129A8`. [Transaction link](https://explorer.zksync.io/tx/0xeb93ddd8c79bdd0beb2b2ca1ba8e58e77c417578d039ecd8095402f459fe8559).
6. Ownership of [Era L2 bridge](https://explorer.zksync.io/address/0x11f943b2c77b743AB90f4A0Ae7d5A4e7FCA3E102) was transferred to [Era L2 ProxyAdmin](https://era.zksync.network/address/0xdB1E46B448e68a5E35CB693a99D59f784aD115CC). [Transanction link](https://explorer.zksync.io/tx/0x927e0591b9f2ef2341b074942f5e058fae14138a4788015b396eef23c01f9e60).
7. Ownership of [Era L2 wETH](https://explorer.zksync.io/address/0x5AEa5775959fBC2557Cc8789bC1bf90A239D9a91) was transferred to [Era L2 ProxyAdmin](https://era.zksync.network/address/0xdB1E46B448e68a5E35CB693a99D59f784aD115CC). [Transaction link](https://explorer.zksync.io/tx/0x993e872dcb300a3f51da9e404115d4b09c85a247a041b8d584558f14fc2ec5af).
8. Ownership of [Cronos L2 Bridge](https://explorer.zkevm.cronos.org/address/0x309429de3621992cb0ab8982a448c9cc5c38405b) was transferred to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897), aliased L2 address `0xA08b9912416E8aDc4D9C21Fae1415d3318A129A8`. [Transaction link](https://explorer.zkevm.cronos.org/tx/0x5233c9560c1c5062fb318a546f0649a7ec16fa31aa9d258d35cb3ac854e5ec54).
9. Ownership of [Cronos L2 UpgradeableBeacon](https://explorer.zkevm.cronos.org/address/0x100af9367f9e27bd1c58a82976059ab67998810f) was transferred to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897), aliased L2 address `0xA08b9912416E8aDc4D9C21Fae1415d3318A129A8`. [Transaction link](https://explorer.zkevm.cronos.org/tx/0xbea11de6a2834ea57922d5f2e80a5d645131c67b5a166695cd1e8ff70669cb8d).
10. [ZK Token](https://explorer.zksync.io/address/0x5A7d6b2F92C77FAD6CCaBd7EE0624E64907Eaf3E) Admin role was granted to the decentralized [ProtocolUpgradeHandler](https://etherscan.io/address/0x8f7a9912416e8AdC4D9c21FAe1415D3318A11897), Minter and Minter Admin roles granted to the [TimelockController](https://explorer.zksync.io/address/0x3E21c654B545Bf6236DC08236169DcF13dA4dDd6) of the decentralized Token Governor, all other admin roles revoked. [Transaction link](https://explorer.zksync.io/tx/0xc1a06497815dd79f6a131bb6f47ded02374c22a06615c1e0e8ca9cf7fcc824e8).

If you want to learn more about connecting to ZKsync Mainnet and Testnet contracts, please visit [docs.zksync.io](https://docs.zksync.io/build/connect-to-zksync).
