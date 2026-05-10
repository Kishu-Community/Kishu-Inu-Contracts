# Kishu Inu Token Deployment And Ownership

This document explains the public deployment and ownership records for the original Kishu Inu (`KISHU`) Ethereum token contract.

It is written for community review. It is not a formal audit and it does not prove that this repository controls any deployed contract or wallet.

## Short Summary

- The KISHU token contract itself appears to be a normal verified Solidity contract, not an upgradeable proxy.
- The verified contract name is `KishuInu`.
- The contract was deployed by the Etherscan-labeled deployer address `Kishu Inu: Deployer`.
- The deployer was funded shortly before deployment by an Etherscan-labeled `Crypto.com 12` address.
- The current token `owner()` resolves to a Safe smart account.
- The Safe is a proxy wallet created through the Safe proxy factory.
- The Safe setup event shows 3 owner addresses with a 2-of-3 threshold.
- This community archive/rebuild does not control or indirectly control the KISHU token contract, deployer, owner Safe, Safe owners, or former team wallets.

## Main Token Contract

- Token contract: [`0xa2b4c0af19cc16a6cfacce81f192b024d625817d`](https://etherscan.io/address/0xa2b4c0af19cc16a6cfacce81f192b024d625817d)
- Token tracker: [`Kishu Inu (KISHU)`](https://etherscan.io/token/0xa2b4c0af19cc16a6cfacce81f192b024d625817d)
- Verified source page: [`KishuInu` source on Etherscan](https://etherscan.io/token/0xa2b4c0af19cc16a6cfacce81f192b024d625817d#code)
- Local source copy: [`KishuInu.sol`](KishuInu.sol)
- Network: Ethereum Mainnet
- Contract name shown by Etherscan: `KishuInu`
- Compiler shown by Etherscan: `v0.6.12+commit.27d51765`
- Optimization shown by Etherscan: disabled
- Source SPDX identifier: `Unlicensed`

## Was The KISHU Token Contract Deployed Through A Proxy?

Based on the verified source and Etherscan contract record, the KISHU token contract itself does not appear to be an upgradeable proxy.

There is no proxy implementation slot, upgrade function, delegatecall proxy wrapper, or proxy admin pattern in the verified `KishuInu` source file.

The important proxy detail is different:

The current owner of the KISHU token contract is a Safe smart account, and Safe wallets are deployed as proxy contracts.

So the plain-English distinction is:

- KISHU token contract: not a proxy, based on the verified source.
- KISHU owner wallet: Safe proxy wallet.

## Deployment Transaction

The KISHU token contract was created in this transaction:

- Deployment transaction: [`0x6f3fd20987f542cedec2e6bfc835427a4f8ee87d1f79cf368de51f9dc289d0d8`](https://etherscan.io/tx/0x6f3fd20987f542cedec2e6bfc835427a4f8ee87d1f79cf368de51f9dc289d0d8)
- Block: [`12260512`](https://etherscan.io/block/12260512)
- Timestamp: `Apr-17-2021 11:11:47 PM UTC`
- From / deployer: [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90ead86fca54ee9a1fe1c55c0ace5896f4319802) (`Kishu Inu: Deployer`)
- Created contract: [`0xa2b4c0af19cc16a6cfacce81f192b024d625817d`](https://etherscan.io/address/0xa2b4c0af19cc16a6cfacce81f192b024d625817d)
- Value sent: `0 ETH`
- Deployment transaction fee shown by Etherscan: `0.376797246 ETH`

The deployment transaction minted the full token supply to the deployer through the constructor:

`100,000,000,000,000,000 KISHU`

Etherscan shows this as a transfer from the zero/null address to `Kishu Inu: Deployer` in the deployment transaction.

## Deployer Address

- Deployer address: [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90ead86fca54ee9a1fe1c55c0ace5896f4319802)
- Etherscan label: `Kishu Inu: Deployer`
- Role observed from public records:
  - Funded shortly before token deployment.
  - Deployed the KISHU token contract.
  - Initially received the full KISHU token supply.
  - Later created the Safe owner wallet.

## Initial Funding Of The Deployer

Etherscan shows the deployer was funded by an address labeled `Crypto.com 12` shortly before token deployment.

- Funding transaction: [`0xac9a84481235e4d4deeab553963b888a2ff74adb2232c7f7dae73230fea1bc1d`](https://etherscan.io/tx/0xac9a84481235e4d4deeab553963b888a2ff74adb2232c7f7dae73230fea1bc1d)
- Timestamp: `Apr-17-2021 11:06:02 PM UTC`
- From: [`0x46340b20830761efd32832A74d7169B29FEB9758`](https://etherscan.io/address/0x46340b20830761efd32832a74d7169b29feb9758) (`Crypto.com 12`)
- To: [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90ead86fca54ee9a1fe1c55c0ace5896f4319802) (`Kishu Inu: Deployer`)
- Value: `1.99 ETH`

This only means that Etherscan labels the funding source as `Crypto.com 12`. It does not identify who controlled the destination deployer wallet.

## Current Token Owner

The `owner()` function was checked on 2026-05-10 and returned:

[`0x0db80dd6316f994c62e117c504f605b2cbf7520d`](https://etherscan.io/address/0x0db80dd6316f994c62e117c504f605b2cbf7520d)

Etherscan identifies this address as a Safe smart account.

This means owner-only KISHU token functions are controlled by that Safe, not by this repository or the current community archive/rebuild.

## Safe Creation

The Safe owner wallet was created in this transaction:

- Safe creation transaction: [`0xf34f45a702fac5d2f8faff1ebf3a1e9b3353c116c9898d6f1c9513542dad0e1f`](https://etherscan.io/tx/0xf34f45a702fac5d2f8faff1ebf3a1e9b3353c116c9898d6f1c9513542dad0e1f)
- Block: [`13443964`](https://etherscan.io/block/13443964)
- Timestamp: `Oct-18-2021 08:33:28 PM UTC`
- From: [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90ead86fca54ee9a1fe1c55c0ace5896f4319802) (`Kishu Inu: Deployer`)
- To: [`0xa6B71E26C5e0845f74c812102Ca7114b6a896AB2`](https://etherscan.io/address/0xa6b71e26c5e0845f74c812102ca7114b6a896ab2) (`Safe: Proxy Factory 1.3.0 Default`)
- Created Safe proxy: [`0x0db80Dd6316F994c62E117C504F605B2cbf7520D`](https://etherscan.io/address/0x0db80dd6316f994c62e117c504f605b2cbf7520d)
- Safe singleton / master copy shown in the `ProxyCreation` event: [`0xd9Db270c1B5E3Bd161E8c8503c55cEABeE709552`](https://etherscan.io/address/0xd9db270c1b5e3bd161e8c8503c55ceabee709552)
- Fallback handler shown in `SafeSetup`: [`0xf48f2B2d2a534e402487b3ee7C18c33Aec0Fe5e4`](https://etherscan.io/address/0xf48f2b2d2a534e402487b3ee7c18c33aec0fe5e4)

The transaction called Safe Proxy Factory function:

`createProxyWithNonce(address _singleton, bytes initializer, uint256 saltNonce)`

## Safe Owners And Threshold

The Safe setup event showed these owners:

- [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90ead86fca54ee9a1fe1c55c0ace5896f4319802)
- [`0x7cA5A38e51c253Ef843e418c0b7115ac1cB35f75`](https://etherscan.io/address/0x7ca5a38e51c253ef843e418c0b7115ac1cb35f75)
- [`0x05C0d0B47e6334c3C170DDB6f3d2Fa7001ff6014`](https://etherscan.io/address/0x05c0d0b47e6334c3c170ddb6f3d2fa7001ff6014)

Threshold:

`2 of 3`

In plain English, the Safe required 2 of the 3 listed owners to approve Safe transactions at setup time.

Reviewers should verify the current Safe owner list and threshold directly on Safe or Etherscan before relying on this historical setup event.

## Safe Owner Address Activity Notes

A live Ethereum RPC check on 2026-05-10 showed the current Safe owner set and threshold still matched the setup event:

- Owners: `0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`, `0x7cA5A38e51c253Ef843e418c0b7115ac1cB35f75`, `0x05C0d0B47e6334c3C170DDB6f3d2Fa7001ff6014`
- Threshold: `2`

Two of the three Safe owner addresses currently show no normal outgoing transaction history, no ETH balance, and no contract code:

- [`0x7cA5A38e51c253Ef843e418c0b7115ac1cB35f75`](https://etherscan.io/address/0x7ca5a38e51c253ef843e418c0b7115ac1cb35f75) - nonce `0`, balance `0 ETH`, no contract code.
- [`0x05C0d0B47e6334c3C170DDB6f3d2Fa7001ff6014`](https://etherscan.io/address/0x05c0d0b47e6334c3c170ddb6f3d2fa7001ff6014) - nonce `0`, balance `0 ETH`, no contract code.

This does not prevent those addresses from being valid Safe owners. Safe owners can sign messages off-chain, and a different address can submit the final Safe transaction on-chain.

Public on-chain records alone do not prove whether the three Safe owner keys were controlled by three separate people, fewer people, one entity, cold/offline signing keys, backup keys, or another arrangement. The lack of transaction history on two owner addresses is worth documenting, but it should be treated as an observation, not proof of shared control.

## What The Token Owner Can Do

The token source includes these owner-only controls:

- `setMaxTxPercent(uint256 maxTxPercent)` - changes the maximum transfer amount as a percentage of total supply.
- `excludeAccount(address account)` - excludes an address from reflection accounting.
- `includeAccount(address account)` - includes an excluded address back into reflection accounting.
- `transferOwnership(address newOwner)` - transfers ownership to a new owner address.
- `renounceOwnership()` - sets owner to the zero address and disables future owner-only calls.

The verified token source does not show owner-only minting, blacklist, pause, upgrade, or fee-change functions.

## What This Community Does Not Control

The current Kishu Community archive/rebuild does not control and does not have indirect control of:

- The KISHU token contract.
- The KISHU deployer address.
- The KISHU owner Safe.
- The Safe owner addresses.
- Former team wallets.
- Former team accounts.
- Legacy project deployments unless explicitly documented in public records.

Because of that, this community archive/rebuild cannot safely claim to:

- Change the original KISHU token contract.
- Force a migration.
- Repair old contracts through owner-only access.
- Move assets from legacy wallets.
- Recover historical losses.
- Verify wallets through private messages, forms, or payments.

## Practical Verification Links

- Token contract: [`0xa2b4c0af19cc16a6cfacce81f192b024d625817d`](https://etherscan.io/address/0xa2b4c0af19cc16a6cfacce81f192b024d625817d)
- Token tracker: [`Kishu Inu (KISHU)`](https://etherscan.io/token/0xa2b4c0af19cc16a6cfacce81f192b024d625817d)
- Verified source: [`KishuInu` source](https://etherscan.io/token/0xa2b4c0af19cc16a6cfacce81f192b024d625817d#code)
- Deployment tx: [`0x6f3fd20987f542cedec2e6bfc835427a4f8ee87d1f79cf368de51f9dc289d0d8`](https://etherscan.io/tx/0x6f3fd20987f542cedec2e6bfc835427a4f8ee87d1f79cf368de51f9dc289d0d8)
- Deployer: [`0x90eAd86FCa54eE9a1FE1C55C0ACE5896f4319802`](https://etherscan.io/address/0x90ead86fca54ee9a1fe1c55c0ace5896f4319802)
- Deployer funding tx: [`0xac9a84481235e4d4deeab553963b888a2ff74adb2232c7f7dae73230fea1bc1d`](https://etherscan.io/tx/0xac9a84481235e4d4deeab553963b888a2ff74adb2232c7f7dae73230fea1bc1d)
- Crypto.com 12 funding address: [`0x46340b20830761efd32832A74d7169B29FEB9758`](https://etherscan.io/address/0x46340b20830761efd32832a74d7169b29feb9758)
- Current owner Safe: [`0x0db80dd6316f994c62e117c504f605b2cbf7520d`](https://etherscan.io/address/0x0db80dd6316f994c62e117c504f605b2cbf7520d)
- Safe creation tx: [`0xf34f45a702fac5d2f8faff1ebf3a1e9b3353c116c9898d6f1c9513542dad0e1f`](https://etherscan.io/tx/0xf34f45a702fac5d2f8faff1ebf3a1e9b3353c116c9898d6f1c9513542dad0e1f)
- Safe Proxy Factory: [`0xa6B71E26C5e0845f74c812102Ca7114b6a896AB2`](https://etherscan.io/address/0xa6b71e26c5e0845f74c812102ca7114b6a896ab2)
- Safe singleton / master copy: [`0xd9Db270c1B5E3Bd161E8c8503c55cEABeE709552`](https://etherscan.io/address/0xd9db270c1b5e3bd161e8c8503c55ceabee709552)
- Safe fallback handler: [`0xf48f2B2d2a534e402487b3ee7C18c33Aec0Fe5e4`](https://etherscan.io/address/0xf48f2b2d2a534e402487b3ee7c18c33aec0fe5e4)

## Notes For Future Review

Useful next checks:

- Confirm whether the Safe owner set or threshold changed after creation.
- Review transactions where the Safe executed owner-only token calls.
- Review deployer transfers after initial supply mint.
- Review relationship between the deployer, Safe, Kishu Crate, Kishuverse, and other Kishu ecosystem contracts.
- Add separate contract folders for each related deployed contract as public evidence is collected.
