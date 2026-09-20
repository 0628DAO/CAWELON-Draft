# CAWELON CORE (CAWELON)

**Status: deployed on Base Mainnet; source verified as an exact match on Blockscout. Not independently audited.**

CAWELON CORE is a fixed-supply, zero-tax ERC-20 core token developed by AssetDeploy LLC for the 0628DAO ecosystem, future autonomous AI agents, and decentralized transaction infrastructure.

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
