# Kishu Takeover ETH

Kishu Takeover is an Ethereum ERC-1155 NFT collection deployed from a Rarible-style `RaribleUserToken` contract.

This collection is important to keep in the archive because the contract still exists on-chain even though the previously checked OpenSea collection route did not show the collection page. Marketplace visibility is not the same thing as contract existence.

## Contract Reference

| Field | Value |
| --- | --- |
| Collection | The takeover collection |
| Chain | Ethereum Mainnet |
| Contract | [`0x8a240d66f09a3a1fc8f108adbce5a5ba61702ced`](https://etherscan.io/token/0x8a240d66f09a3a1fc8f108adbce5a5ba61702ced) |
| Source file | [`RaribleUserToken.sol`](RaribleUserToken.sol) |
| ABI | [`ABI.json`](ABI.json) |
| Contract name from source | `RaribleUserToken` |
| On-chain name | `The takeover collection` |
| On-chain symbol | `CPTK` |
| Deployer | [`0x3141FCef2fCf8ede0470fE2B5afb497a0F70102d`](https://etherscan.io/address/0x3141FCef2fCf8ede0470fE2B5afb497a0F70102d) |
| Current owner checked | [`0x99834733C91aAE2f5BB0725105c9E843Cb297A27`](https://etherscan.io/address/0x99834733C91aAE2f5BB0725105c9E843Cb297A27) |
| Creation block | [`13495309`](https://etherscan.io/block/13495309) |
| Creation transaction | [`0xe47221897e4969172e17190b34ca73ef92098f84e70a0edbf4f34c225d299480`](https://etherscan.io/tx/0xe47221897e4969172e17190b34ca73ef92098f84e70a0edbf4f34c225d299480) |
| Alternate marketplace reference | [PulseMarket collection](https://pulsemarket.app/collection/0x8a240d66f09a3a1fc8f108adbce5a5ba61702ced) |

## Related Public Archive Repo

- [kishucrate-interface-public](https://github.com/Kishu-Community/kishucrate-interface-public)

Recovered community notes place Kishu Takeover in or around the original Kishu Crate release context. The Kishu Crate public archive repo is therefore the related platform/context repo, while this folder keeps the Takeover collection contract facts separate.

## Ownership Note

The current `owner()` value is `0x99834733C91aAE2f5BB0725105c9E843Cb297A27`, while the creation transaction was sent by `0x3141FCef2fCf8ede0470fE2B5afb497a0F70102d`.

That means the current owner is not the original deployer address. The exact ownership-transfer event history still needs to be pulled from a reliable indexed log source and documented separately.

## Community Attribution To Verify

Recovered community notes identify this collection as presented at the time as created or owned by the team member known as `Captain Kishu`.

That is a historical attribution note, not on-chain proof of identity. The on-chain facts verified in this folder are the contract address, deployer address, and current `owner()` address listed above.

## KISHU Token Integration

No direct integration with the original KISHU ERC-20 token was found in this contract.

The source does not show logic to require KISHU for minting, stake KISHU, reward KISHU, read KISHU balances, transfer KISHU, or burn KISHU.

## Files

- [`RaribleUserToken.sol`](RaribleUserToken.sol) - verified Solidity source copied from Etherscan.
- [`ABI.json`](ABI.json) - ABI copied from Etherscan.
- [`Contract-Breakdown.md`](Contract-Breakdown.md) - plain-English contract notes.
- [`source-metadata.json`](source-metadata.json) - source retrieval metadata.
