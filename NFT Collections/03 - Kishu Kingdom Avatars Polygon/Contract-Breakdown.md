# Kishu Kingdom Avatars Contract Breakdown

## What It Is

This is a Polygon ERC-721 enumerable NFT contract. The source pattern is similar to a standard public mint contract with owner-only controls.

The deployed contract source name is `KishuKingdomAvatars`.

## Minting Logic

The public `mint(address _to, uint256 _mintAmount)` function:

- Requires the contract to not be paused.
- Requires `_mintAmount` to be greater than zero.
- Requires `_mintAmount` to be no more than `maxMintAmount`.
- Requires `totalSupply() + _mintAmount` to stay at or below `maxSupply`.
- Requires non-owner callers to pay at least `cost * _mintAmount`.
- Mints token IDs sequentially.

Current read values checked on May 11, 2026:

- `maxSupply()`: `2222`
- `totalSupply()`: `2222`
- `cost()`: `0`
- `paused()`: `false`
- `maxMintAmount()`: `2222`

## Owner Controls

The owner can:

- Change metadata location with `setBaseURI`.
- Change metadata extension with `setBaseExtension`.
- Pause or unpause minting with `pause`.
- Withdraw native chain currency held by the contract with `withdraw`.
- Transfer or renounce ownership.

The owner cannot change the original KISHU ERC-20 contract from this NFT contract.

## Metadata

The token URI is built from:

- `baseURI()`: `https://ipfs.io/ipfs/QmeWKY8a2TwpxDUGyykbphZYe29x7ktPR4NpUveodvEpu1/`
- token ID
- `baseExtension()`: `.json`

Because the owner can change the base URI and extension, metadata control depends on the current owner address unless ownership has been renounced.

## KISHU ERC-20 Relationship

No reference to the original KISHU ERC-20 token address was found in this Solidity source.

This contract should not be described as staking, paying, burning, or controlling the original KISHU token unless separate verified contracts or transactions prove that behavior.

## Review Notes

This folder should not be used as proof that a Kishu Kingdom game existed or was delivered. The NFT contract can prove the avatar collection exists on Polygon; game files, playable deployments, and project delivery claims require separate evidence.
