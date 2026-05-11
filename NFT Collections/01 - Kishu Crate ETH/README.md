# Kishu Crate ETH

Kishu Crate is an Ethereum ERC-1155 NFT collection deployed from a Rarible-style `RaribleUserToken` contract.

## Contract Reference

| Field | Value |
| --- | --- |
| Collection | Kishu Crate |
| Chain | Ethereum Mainnet |
| Contract | [`0x7ba9a9d77ac6ddcb4d8b63665ca985a2fec6430f`](https://etherscan.io/token/0x7ba9a9d77ac6ddcb4d8b63665ca985a2fec6430f) |
| Source file | [`RaribleUserToken.sol`](RaribleUserToken.sol) |
| ABI | [`ABI.json`](ABI.json) |
| Contract name from source | `RaribleUserToken` |
| On-chain name | `Kishu Crate` |
| On-chain symbol | `KISHU` |
| Current owner checked | [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802) |
| Creation block | [`13489134`](https://etherscan.io/block/13489134) |
| Creation transaction | [`0xb230eadb255176fd8be88b6a95069536126e82a0bad6e818617ee3ddc325820a`](https://etherscan.io/tx/0xb230eadb255176fd8be88b6a95069536126e82a0bad6e818617ee3ddc325820a) |
| Marketplace reference | [OpenSea Kishu Crate](https://opensea.io/collection/kishu-crate) |

## KISHU Token Integration

No direct integration with the original KISHU ERC-20 token was found in this contract.

The `KISHU` value here is the NFT collection symbol returned by this ERC-1155 contract. It does not mean the NFT contract requires or controls the original KISHU token contract.

The source does not show logic to:

- Require KISHU for minting.
- Stake KISHU.
- Reward KISHU.
- Read KISHU balances.
- Transfer KISHU.
- Burn KISHU.

## Control Notes

The current `owner()` can use owner-only functions in the Rarible-style contract, including owner-gated minting, signer management, and URI configuration functions exposed by the source.

This repository does not control this contract or the current owner address.

## Files

- [`RaribleUserToken.sol`](RaribleUserToken.sol) - verified Solidity source copied from Etherscan.
- [`ABI.json`](ABI.json) - ABI copied from Etherscan.
- [`Contract-Breakdown.md`](Contract-Breakdown.md) - plain-English contract notes.
- [`source-metadata.json`](source-metadata.json) - source retrieval metadata.
