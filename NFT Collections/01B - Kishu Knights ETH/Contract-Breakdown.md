# Kishu Knights Contract Breakdown

## What It Is

This is a Rarible-style ERC-1155 NFT contract. It shares the same verified source pattern as Kishu Crate and Kishu Takeover.

The deployed contract source name is `RaribleUserToken`.

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

- `name()`: `Kishu Inu 3D Trading Cards`
- `symbol()`: `KTC`
- `contractURI()`: `https://api-mainnet.rarible.com/contractMetadata/{address}`
- `tokenURIPrefix()`: `ipfs:/`

## KISHU ERC-20 Relationship

No reference to the original KISHU ERC-20 token address was found in this Solidity source.

This contract should not be described as staking, paying, burning, or controlling the original KISHU token unless separate verified contracts or transactions prove that behavior.

## Review Notes

This contract is owner-controlled. The current owner should be checked directly on Etherscan before trusting any claim about metadata control, new minting, signer authority, or future use.
