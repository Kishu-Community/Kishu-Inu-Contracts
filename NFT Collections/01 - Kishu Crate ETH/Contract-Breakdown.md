# Kishu Crate Contract Breakdown

## What It Is

This is a Rarible-style ERC-1155 NFT contract. ERC-1155 allows one contract to manage multiple token IDs, and each token ID can have a supply greater than one.

The deployed contract source name is `RaribleUserToken`, not a custom Kishu-only NFT engine.

## Important Public Functions

- `owner()` returns the current owner/admin address.
- `transferOwnership(address newOwner)` lets the current owner transfer control.
- `renounceOwnership()` lets the current owner remove owner-only control.
- `mint(...)` is owner-only in `RaribleUserToken` and also requires a valid signer signature from the Rarible-style mint flow.
- `addSigner(address account)` and `removeSigner(address account)` manage signer permissions.
- `setTokenURIPrefix(string tokenURIPrefix)` lets the owner change the token URI prefix.
- `setContractURI(string contractURI)` lets the owner change collection-level metadata URI.
- `burn(address owner, uint256 id, uint256 value)` lets a holder or approved operator burn ERC-1155 balances.
- `safeTransferFrom(...)` and `safeBatchTransferFrom(...)` are standard ERC-1155 transfer functions.

## Metadata

Current read-only values checked on May 11, 2026:

- `name()`: `Kishu Crate`
- `symbol()`: `KISHU`
- `contractURI()`: `https://api-mainnet.rarible.com/contractMetadata/{address}`
- `tokenURIPrefix()`: `ipfs:/`

## KISHU ERC-20 Relationship

No reference to the original KISHU ERC-20 token address was found in this Solidity source.

This NFT contract should not be described as staking, paying, burning, or controlling the original KISHU token unless separate verified contracts or transactions prove that behavior.

## Review Notes

Because this is an owner-controlled NFT contract, ownership matters. Anyone reviewing this collection should verify the current `owner()` on Etherscan before trusting claims about current control, metadata updates, or future use.
