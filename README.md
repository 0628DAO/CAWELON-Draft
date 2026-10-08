# CAWELON CORE (CAWELON)


**Status: deployed on Base Mainnet; source verified as an exact match on Blockscout. Not independently audited.**


CAWELON CORE is a fixed-supply, zero-tax ERC-20 core token developed by AssetDeploy LLC for the 0628DAO ecosystem, future autonomous AI agents, and decentralized transaction infrastructure.


## ThreeCore direction — CAWELON

### CAWELON AI-agent system definition

The development goal is a system in which the CAWELON AI agent uses external
dApps within predefined funding, permission and operating-policy limits,
records realized profits and losses, and uses eligible realized earnings to
buy back and burn CAWELON under specified conditions. Fund movements and execution
results are to be published with supporting records so that third parties can
verify them.

**Operating policy:** CAWELON focuses on higher-return opportunities. This is a decision-making
orientation, not a promise of returns or a fixed execution strategy.

**Shared design, independent resources:** CAWELON is intended to use the common
ThreeCore system design while keeping its funds, permissions and accounting
separate from the other two tokens. Each agent analyzes, decides and executes
for its own token. Direct dividends to holders are not part of this design.

**Design items still to be specified:** wallet count and structure, supported
dApps, funding and transaction limits, profit-allocation ratios, decision and
settlement rules, profit-calculation methods, and failure/recovery behavior.
No wallet count or allocation percentage is fixed by this definition.

**Development status:** this section defines the target agent/dApp system.
The base ERC-20 token's deployment status is documented separately below.
Token deployment and promotional films do not establish that autonomous dApp
execution, profit accounting or automated buyback and burn are complete or
running in production. Implementation, testing and operational evidence must
be published separately. x402 is not a prerequisite.

### 日本語：CAWELONの定義と基本方針

CAWELON AIエージェントが、事前に定めた資金・権限・運用方針の範囲で外部dAppを利用し、
確定した損益を記録し、所定の条件を満たした実現収益からCAWELONの買戻しとBurnを実行する。
その資金移動と実行結果を根拠となる記録とともに公開し、第三者が検証できるシステムを目指します。

- **運用方針：** 高リターン志向。利益を保証する表現や、確定した運用戦略ではありません。
- **共通設計と独立性：** ThreeCore共通の設計を採用し、資金・権限・会計は他の2トークンから独立させます。各AIが自ら分析・判断・実行します。
- **価値還元：** 自トークンのBuyback & Burnを想定し、ホルダーへの直接配当は想定しません。
- **未確定の設計項目：** ウォレット数・構成、利用dApp、金額上限、利益配分率、判断・決済条件、利益計算、失敗時の処理・復旧方法です。
- **開発状況：** これは開発するシステムの定義です。基本トークンの配備と、自律運用システムの実装・検証・本番稼働は別に示します。

Despite this repository's `-Draft` name, `contracts/CAWELONCore.sol` is the
current token implementation described below. Root-level draft files are
historical references.

See [ThreeCore shared definition, wallet workflow and implementation boundaries](https://github.com/0628DAO/0628DAO-Protocol/blob/main/docs/THREECORE.md).

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
