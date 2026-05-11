# Kishuverse ETH

Kishuverse is an Ethereum ERC-721 NFT collection with paid minting logic.

## Contract Reference

| Field | Value |
| --- | --- |
| Collection | Kishuverse |
| Chain | Ethereum Mainnet |
| Contract | [`0x0be5dd8dc316a936942b1f58667c9ea1ebb71e07`](https://etherscan.io/token/0x0be5dd8dc316a936942b1f58667c9ea1ebb71e07) |
| Source file | [`Kishuverse.sol`](Kishuverse.sol) |
| ABI | [`ABI.json`](ABI.json) |
| Contract name from source | `Kishuverse` |
| On-chain name | `Kishuverse` |
| On-chain symbol | `Kishuverse` |
| Deployer/current owner checked | [`0xc38568F9C9080de06fA924c4353F8616aa502c1f`](https://etherscan.io/address/0xc38568F9C9080de06fA924c4353F8616aa502c1f) |
| Creation block | [`13532364`](https://etherscan.io/block/13532364) |
| Creation transaction | [`0x715189797475a7320ab1a6f4f4919e475075fb6fecf570d2fe5da75e1569c8d6`](https://etherscan.io/tx/0x715189797475a7320ab1a6f4f4919e475075fb6fecf570d2fe5da75e1569c8d6) |
| Marketplace reference | [OpenSea Kishuverse](https://opensea.io/collection/kishuverse) |

## Related Public Archive Repo

- [kishuverse-interface-public](https://github.com/Kishu-Community/kishuverse-interface-public)

That repo documents the recovered Kishuverse interface and the difference between the historical wallet/minting frontend and the current read-only public archive. It is separate from this NFT contract archive and does not give control over this deployed NFT contract.

## Current Read Values

Checked by read-only on-chain calls on May 11, 2026:

- `totalSupply()`: `7726`
- `maxSupply()`: `8888`
- `cost()`: `0.038 ETH`
- `paused()`: `false`
- `maxMintAmount()`: `10`
- `baseURI()`: `https://ipfs.io/ipfs/QmcJnxcNDuirzMzX6YJABWdV3KJ6zyqRFfxuB423PsCP6r/`
- `baseExtension()`: `.json`

## KISHU Token Integration

No direct integration with the original KISHU ERC-20 token was found in this contract.

The source does not show logic to require KISHU for minting, stake KISHU, reward KISHU, read KISHU balances, transfer KISHU, or burn KISHU.

Minting is priced in ETH through the `cost` value.

## Control Notes

The current `owner()` can call owner-only functions including:

- `setmaxMintAmount(uint256 _newmaxMintAmount)`
- `setBaseURI(string memory _newBaseURI)`
- `setBaseExtension(string memory _newBaseExtension)`
- `pause(bool _state)`
- `withdraw()`
- `transferOwnership(address newOwner)`
- `renounceOwnership()`

This repository does not control this contract or the current owner address.

## Community Attribution To Verify

Recovered community notes identify Kishuverse as presented at the time as created or owned by the team members known as `Robinhood` and `Mo Kishu`.

That is a historical attribution note, not on-chain proof of identity or shared wallet control. The on-chain facts verified in this folder are the contract address, deployer address, and current `owner()` address listed above.

## Follow-Up

Recovered discussion notes suggest there may be a historical connection between a former homepage donation wallet and Kishuverse-related wallet activity. That connection is not verified in this folder yet. It should be documented only after the old donation wallet address and matching public transactions are confirmed.

## Files

- [`Kishuverse.sol`](Kishuverse.sol) - verified Solidity source copied from Etherscan.
- [`ABI.json`](ABI.json) - ABI copied from Etherscan.
- [`Contract-Breakdown.md`](Contract-Breakdown.md) - plain-English contract notes.
- [`source-metadata.json`](source-metadata.json) - source retrieval metadata.
