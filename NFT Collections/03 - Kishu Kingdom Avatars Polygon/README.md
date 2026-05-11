# Kishu Kingdom Avatars Polygon

Kishu Kingdom Avatars is a Polygon ERC-721 NFT collection associated with the later Kishu Kingdom / avatar project era.

The Solidity source in this folder was copied from Sourcify `partial_match`, not directly from a scripted Polygonscan scrape.

## Contract Reference

| Field | Value |
| --- | --- |
| Collection | KishuKingdomAvatars |
| Chain | Polygon |
| Contract | [`0xad411f5a8ba84533b350a2e50a46ba7511edfcae`](https://polygonscan.com/token/0xad411f5a8ba84533b350a2e50a46ba7511edfcae) |
| Source file | [`KishuKingdomAvatars.sol`](KishuKingdomAvatars.sol) |
| ABI | [`ABI.json`](ABI.json) |
| Source archive | [Sourcify partial match](https://repo.sourcify.dev/contracts/partial_match/137/0xad411f5a8ba84533b350a2e50a46ba7511edfcae/) |
| Contract name from source | `KishuKingdomAvatars` |
| On-chain name | `KishuKingdomAvatars` |
| On-chain symbol | `KKA` |
| Current owner checked | [`0x35e45f9DA89143F5aB6ea705784beB65482875fA`](https://polygonscan.com/address/0x35e45f9DA89143F5aB6ea705784beB65482875fA) |
| Marketplace reference | [OpenSea Kishu Kingdom Avatars](https://opensea.io/collection/kishukingdomavatars) |

## Current Read Values

Checked by read-only on-chain calls on May 11, 2026:

- `totalSupply()`: `2222`
- `maxSupply()`: `2222`
- `cost()`: `0`
- `paused()`: `false`
- `maxMintAmount()`: `2222`
- `baseURI()`: `https://ipfs.io/ipfs/QmeWKY8a2TwpxDUGyykbphZYe29x7ktPR4NpUveodvEpu1/`
- `baseExtension()`: `.json`

## KISHU Token Integration

No direct integration with the original KISHU ERC-20 token was found in this contract.

The source does not show logic to require KISHU for minting, stake KISHU, reward KISHU, read KISHU balances, transfer KISHU, or burn KISHU.

## Project Context

Kishu Kingdom Avatars were associated with the broader Kishu Kingdom project era.

Public Kishu materials described Kishu Kingdom as a play-to-earn trading card game developed by Main Leaf, and Main Leaf-related public profiles have listed a Kishu Kingdom teaser/trailer reference.

References:

- Kishu Medium announcement: <https://kishuinu.medium.com/dubai-expo-kishu-kingdom-34b1201a6d6b>
- Main Leaf ArtStation profile: <https://mainleaf.artstation.com/>
- gamescom latam Main Leaf profile: <https://b2b.latam.gamescom.global/companies/2704>
- Kishu Kingdom YouTube trailer: <https://www.youtube.com/watch?v=GEA57Qflivg>
- NOWPayments interview: <https://nowpayments.io/blog/meet-kishu-an-exclusive-interview-with-kishu-inu-crypto>

This NFT contract source does not itself contain game logic, backend integration, Main Leaf references, KISHU token integration, or proof of a delivered playable game.

## Control Notes

The current `owner()` can call owner-only functions including metadata changes, pause/unpause, withdrawal, ownership transfer, and ownership renounce functions.

This repository does not control this contract or the current owner address.

## Follow-Up

- Record the Polygon creation transaction if a reliable explorer or archive source is available.
- Document the Kishu Kingdom / Bybit avatar context only from recoverable public sources.
- Keep game claims separate from NFT contract facts unless actual game files, deployments, or contracts are recovered.

## Files

- [`KishuKingdomAvatars.sol`](KishuKingdomAvatars.sol) - Solidity source copied from Sourcify partial match.
- [`ABI.json`](ABI.json) - ABI copied from Sourcify metadata.
- [`sourcify-metadata.json`](sourcify-metadata.json) - full Sourcify metadata.
- [`Contract-Breakdown.md`](Contract-Breakdown.md) - plain-English contract notes.
- [`source-metadata.json`](source-metadata.json) - source retrieval metadata.
