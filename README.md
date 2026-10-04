# CAWELON CORE (CAWELON)


**Status: deployed on Base Mainnet; source verified as an exact match on Blockscout. Not independently audited.**


CAWELON CORE is a fixed-supply, zero-tax ERC-20 core token developed by AssetDeploy LLC for the 0628DAO ecosystem, future autonomous AI agents, and decentralized transaction infrastructure.


## ThreeCore direction — CAWELON

CAWELON is the higher-holder-return identity within ThreeCore. The six-minute
film illustrates decentralized trading; the separate 120-second wallet special
introduces one dedicated wallet per agent, backend signing within authorized
limits, settlement accounting and own-token buyback and burn.

Dedicated-wallet coding is underway. The film's profitable BTC long at ×100 is
an illustration, not the current runtime configuration or a record of results.
“High dividends” expresses the narrative goal; this token has no automatic
dividend mechanism. Trading, buybacks and liquidity operations require separate
software. x402 is not a prerequisite.

CAWELONはホルダーへの高い還元を重視。専用ウォレットは開発中で、
各自の実現収益による自トークンのBuyback & Burnを目指します。
動画の100倍取引は説明用の場面で、現在の運用設定を示すものではありません。

Despite this repository's `-Draft` name, `contracts/CAWELONCore.sol` is the
current token implementation described below. Root-level draft files are
historical references.

See [ThreeCore direction, wallet workflow and implementation boundaries](https://github.com/0628DAO/0628DAO-Protocol/blob/main/docs/THREECORE.md).

## Mainnet deployment


| Item | Value |
|---|---|
| Network | Base Mainnet (chain ID 8453) |
| Contract | [`0xB4654b5a4617Fe2c27a0DD6EAEe98F8AA941b895`](https://base.blockscout.com/address/0xB4654b5a4617Fe2c27a0DD6EAEe98F8AA941b895?tab=contract) |
| Deployment transaction | [`0x13ff6cae2e986d729aa76bf348f04186dff1bd80aae6fc8d684b0d559be8fd28`](https://base.blockscout.com/tx/0x13ff6cae2e986d729aa76bf348f04186dff1bd80aae6fc8d684b0d559be8fd28) |
| Initial holder | `0xfbE494B465efe6d0Daff80dC715302d0Fa0Ac5d9` |
| Initial supply | 420,000,000,000,000 CAWELON |
| Compiler | Solidity 0.8.34 |
| Optimizer / EVM | Disabled / default |
| Source verification | Blockscout exact match |
| Project page | [assetdeploy.xyz/#caweloncore](https://assetdeploy.xyz/#caweloncore) |


## Aerodrome liquidity

| Item | Value |
|---|---|
| DEX | Aerodrome Finance |
| Pool type | Volatile (vAMM) |
| Pair | CAWELON/USDC |
| Pool | [`0x5445b0F683c74Aff048149bb9e0865d05A85b0b4`](https://base.blockscout.com/address/0x5445b0F683c74Aff048149bb9e0865d05A85b0b4) |
| Initial liquidity | 4,200,000,000,000 CAWELON + 100 USDC |
| Add-liquidity transaction | [`0xccb3bd357e3b83f12a891e0ec4583c203ce163899ee00517dea31c5cb0cb0da3`](https://base.blockscout.com/tx/0xccb3bd357e3b83f12a891e0ec4583c203ce163899ee00517dea31c5cb0cb0da3) |
| USDC | [Canonical Base USDC](https://base.blockscout.com/address/0x833589fCD6eDb6E08f4c7C32D4f71b54bdA02913) |

This pool is external to the CAWELON token contract. Pool balances and price may change through trading and later liquidity changes.

## Confirmed token specification


| Item | Value |
|---|---|
| Contract | `CAWELONCore` |
| Name | CAWELON CORE |
| Symbol | CAWELON |
| Decimals | 18 |
| Transfer / buy / sell tax | 0% |
| Additional minting | None |
| Burn | Holder burn and allowance-based `burnFrom`, as in DATCORE |
| Permit | EIP-2612, domain name `CAWELON CORE` |
| Owner / admin / pause / upgrade / proxy | None |


The entire supply was minted once to the initial-holder address. The contract contains no vesting, automatic distribution, price support, liquidity, blacklist, pause, upgrade, or administrator mint mechanism. Any liquidity position is external to the token contract.


## Base Sepolia reference


The same implementation was deployed and exact-match verified on Base Sepolia before mainnet release:


- Contract: [`0x9c2aeb2f80e074DaC065d0E5dB41c2f01feD280f`](https://base-sepolia.blockscout.com/address/0x9c2aeb2f80e074DaC065d0E5dB41c2f01feD280f?tab=contract)
- Network: Base Sepolia (chain ID 84532)


## Provenance and scope


Base source: [0628DAO/DAT](https://github.com/0628DAO/DAT/tree/0aa811b9c7607d7af6129a943cca8be72974a59b), `contracts/DATCore.sol`. Token logic is unchanged except for the contract/error names, token name, symbol, permit domain, and initial supply. DATCORE's MIT license and pinned OpenZeppelin/compiler dependencies are retained.


Prior Draft documentation is archived at [docs/legacy-draft-readme.md](docs/legacy-draft-readme.md). Existing token deployments are not migrated or converted by this contract.


## Local checks


Use Node.js 22 or newer:


```sh
npm ci
npm run check
```


The test suite covers metadata, supply, allocation, transfers, allowances, holder burns, authorized and unauthorized `burnFrom`, EIP-2612 permits, replay and expiry rejection, EIP-712 domain data, and the absence of privileged functions.

Passing local checks and explorer verification are not substitutes for an independent security audit. Never share keys, seed phrases, keystore passwords, or secret screenshots.

© AssetDeploy LLC. MIT License applies to the DATCORE-derived implementation.
