# Kishu-Related NFT Collections

This folder archives NFT collection contracts connected to Kishu-branded project history.

These contracts are documented separately from the original KISHU ERC-20 token because the NFT contracts reviewed here do not directly control, modify, stake, burn, reward, or transfer the original KISHU token contract at `0xa2b4c0af19cc16a6cfacce81f192b024d625817d`.

## Collections In This Folder

### 01 - Kishu Crate ETH

- Folder: [Kishu Crate ETH](01%20-%20Kishu%20Crate%20ETH/)
- Chain: Ethereum
- Contract: [`0x7ba9a9d77ac6ddcb4d8b63665ca985a2fec6430f`](https://etherscan.io/token/0x7ba9a9d77ac6ddcb4d8b63665ca985a2fec6430f)
- Current owner/admin checked: [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802)
- Notes: Rarible-style ERC-1155 collection.

### 01A - Kishu Takeover ETH

- Folder: [Kishu Takeover ETH](01A%20-%20Kishu%20Takeover%20ETH/)
- Chain: Ethereum
- Contract: [`0x8a240d66f09a3a1fc8f108adbce5a5ba61702ced`](https://etherscan.io/token/0x8a240d66f09a3a1fc8f108adbce5a5ba61702ced)
- Current owner/admin checked: [`0x99834733C91aAE2f5BB0725105c9E843Cb297A27`](https://etherscan.io/address/0x99834733C91aAE2f5BB0725105c9E843Cb297A27)
- Notes: Rarible-style ERC-1155 collection. Current owner differs from deployer.

### 01B - Kishu Knights ETH

- Folder: [Kishu Knights ETH](01B%20-%20Kishu%20Knights%20ETH/)
- Chain: Ethereum
- Contract: [`0x3f07e5d9fdbdb4baf018eb466faa1754d882572e`](https://etherscan.io/token/0x3f07e5d9fdbdb4baf018eb466faa1754d882572e)
- Current owner/admin checked: [`0x629CeCc4cBfbf5984139B6afB68c1dbaC82Bc4D4`](https://etherscan.io/address/0x629CeCc4cBfbf5984139B6afB68c1dbaC82Bc4D4)
- Notes: Rarible-style ERC-1155 collection.

### 02 - Kishuverse ETH

- Folder: [Kishuverse ETH](02%20-%20Kishuverse%20ETH/)
- Chain: Ethereum
- Contract: [`0x0be5dd8dc316a936942b1f58667c9ea1ebb71e07`](https://etherscan.io/token/0x0be5dd8dc316a936942b1f58667c9ea1ebb71e07)
- Current owner/admin checked: [`0xc38568F9C9080de06fA924c4353F8616aa502c1f`](https://etherscan.io/address/0xc38568F9C9080de06fA924c4353F8616aa502c1f)
- Notes: ERC-721 collection with paid minting logic.

### 03 - Kishu Kingdom Avatars Polygon

- Folder: [Kishu Kingdom Avatars Polygon](03%20-%20Kishu%20Kingdom%20Avatars%20Polygon/)
- Chain: Polygon
- Contract: [`0xad411f5a8ba84533b350a2e50a46ba7511edfcae`](https://polygonscan.com/token/0xad411f5a8ba84533b350a2e50a46ba7511edfcae)
- Current owner/admin checked: [`0x35e45f9DA89143F5aB6ea705784beB65482875fA`](https://polygonscan.com/address/0x35e45f9DA89143F5aB6ea705784beB65482875fA)
- Notes: Polygon ERC-721 avatar collection. Source archived from Sourcify partial match.

## Verification Notes

- Ethereum source files and ABIs were copied from Etherscan verified contract pages.
- The Kishu Kingdom Avatars source was copied from Sourcify `partial_match` because scripted Polygonscan source retrieval was not reliable.
- Current owner/admin values were checked with read-only on-chain calls on May 11, 2026.
- Marketplace pages can change independently from the blockchain. If a collection page disappears from OpenSea, that does not delete the deployed smart contract.

## Open Follow-Ups

- Confirm historical marketplace metadata and collection descriptions from archived pages where possible.
- Pull and document Kishu Takeover ownership-transfer events with a reliable indexed log source.
- Compare Kishuverse deployer/owner and withdraw behavior against any recovered historical donation wallet records from old homepage materials.
- Record the Polygon creation transaction for Kishu Kingdom Avatars if a reliable explorer or archive source is available.
