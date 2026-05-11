# Kishuverse Contract Breakdown

## What It Is

This is an ERC-721 enumerable NFT contract. ERC-721 means each token ID is unique. The contract includes public minting, owner-only controls, metadata URI settings, and a withdrawal function.

The deployed contract source name is `Kishuverse`.

## Minting Logic

The public `mint(address _to, uint256 _mintAmount)` function:

- Requires the contract to not be paused.
- Requires `_mintAmount` to be greater than zero.
- Requires `_mintAmount` to be no more than `maxMintAmount`.
- Requires `totalSupply() + _mintAmount` to stay at or below `maxSupply`.
- Requires non-owner callers to pay at least `cost * _mintAmount`.
- Mints token IDs sequentially.

Current read values checked on May 11, 2026:

- `maxSupply()`: `8888`
- `totalSupply()`: `7726`
- `cost()`: `38000000000000000 wei` (`0.038 ETH`)
- `paused()`: `false`
- `maxMintAmount()`: `10`

## Owner Controls

The owner can:

- Change max mint amount with `setmaxMintAmount`.
- Change metadata location with `setBaseURI`.
- Change metadata extension with `setBaseExtension`.
- Pause or unpause minting with `pause`.
- Withdraw ETH held by the contract with `withdraw`.
- Transfer or renounce ownership.

The owner cannot change the original KISHU ERC-20 contract from this NFT contract.

## Metadata

The token URI is built from:

- `baseURI()`: `https://ipfs.io/ipfs/QmcJnxcNDuirzMzX6YJABWdV3KJ6zyqRFfxuB423PsCP6r/`
- token ID
- `baseExtension()`: `.json`

Because the owner can change the base URI and extension, metadata control depends on the current owner address unless ownership has been renounced.

## KISHU ERC-20 Relationship

No reference to the original KISHU ERC-20 token address was found in this Solidity source.

This contract should not be described as staking, paying, burning, or controlling the original KISHU token unless separate verified contracts or transactions prove that behavior.

## Review Notes

The most important review surfaces are current owner control, minting status, ETH withdrawal behavior, metadata mutability, and whether any separate frontend points users at the correct contract.
