# Kishu Inu ETH Token

This folder documents the original Kishu Inu (`KISHU`) ERC-20 token contract deployed on Ethereum Mainnet.

## Contract Reference

- Token: Kishu Inu (`KISHU`)
- Network: Ethereum Mainnet
- Contract: `0xa2b4c0af19cc16a6cfacce81f192b024d625817d`
- Etherscan: https://etherscan.io/token/0xa2b4c0af19cc16a6cfacce81f192b024d625817d
- Source file: [Kishu.sol](Kishu.sol)
- Etherscan contract name: `KishuInu`
- Solidity compiler shown by Etherscan: `v0.6.12+commit.27d51765`
- Optimization shown by Etherscan: disabled
- Source SPDX identifier: `Unlicensed`

Live `owner()` check on 2026-05-10 returned:

`0x0db80dd6316f994c62e117c504f605b2cbf7520d`

That address should be reviewed separately as an owner/admin Safe or wallet. This repository does not prove control over that address.

## High-Level Summary

The KISHU token is a reflection-style ERC-20 token. On normal transfers, the contract takes a 2% transfer fee and redistributes that fee across holders through reflection accounting. The fee is not sent to a team wallet in this source code. Instead, the reflected supply accounting is adjusted so non-excluded holders receive a proportional balance increase over time.

The contract is not a proxy and does not include upgrade logic in the verified source.

## Token Metadata

The contract hardcodes:

- Name: `Kishu Inu`
- Symbol: `KISHU`
- Decimals: `9`
- Max total supply: `100,000,000,000,000,000 KISHU`

The raw Solidity total supply is:

`100000000000 * 10**6 * 10**9`

Because the token has 9 decimals, that equals `100,000,000,000,000,000` displayed KISHU.

## Transfer Fee / Reflection Logic

The transfer fee is defined in `_getTValues`:

- `tFee = tAmount / 100 * 2`
- `tTransferAmount = tAmount - tFee`

In plain terms:

- Sender balance is reduced by the full transfer amount.
- Recipient receives 98% of the transfer amount.
- 2% is reflected to holders by reducing `_rTotal` and increasing `_tFeeTotal`.

This is why swaps involving KISHU may require slippage: the amount received by the recipient is lower than the amount sent because of the transfer fee.

## Reflection Accounting

The contract uses two accounting systems:

- `_rOwned` tracks reflected balances.
- `_tOwned` tracks token balances for addresses excluded from reflections.

Most holders are tracked through reflected balances. When the contract calculates a balance for a normal holder, it converts the reflected amount back into token units using the current reflection rate.

The `totalFees()` function returns `_tFeeTotal`, which is the cumulative amount reflected through fees and manual reflection calls.

## Owner-Controlled Functions

The contract inherits `Ownable`, so owner-only functions can only be called by the current owner address.

Owner-controlled functions in this token include:

- `setMaxTxPercent(uint256 maxTxPercent)` - changes the maximum transfer amount as a percentage of total supply.
- `excludeAccount(address account)` - excludes an address from reflection accounting.
- `includeAccount(address account)` - includes an excluded address back into reflection accounting.
- `transferOwnership(address newOwner)` - transfers ownership to another address.
- `renounceOwnership()` - sets owner to the zero address and disables future owner-only calls.

These controls matter because they can affect transfer limits and reflection accounting behavior.

## Max Transaction Amount

The initial `_maxTxAmount` is:

`100000000 * 10**6 * 10**9`

With 9 decimals, this equals:

`100,000,000,000,000 KISHU`

That is 0.1% of the max total supply.

The `_transfer` function applies this max transaction check only when neither the sender nor recipient is the owner:

`if(sender != owner() && recipient != owner()) require(amount <= _maxTxAmount, "Transfer amount exceeds the maxTxAmount.");`

The owner can change `_maxTxAmount` through `setMaxTxPercent`.

## Functions The Source Does Not Show

Based on the verified source in this folder, the KISHU token contract does not appear to include:

- A mint function.
- A standard burn function.
- A blacklist function.
- A pause/unpause function.
- A tax wallet or treasury fee receiver.
- Proxy upgrade logic.
- A function to change the 2% reflection fee.

This does not mean there are no risks. It means those specific functions are not present in the verified token source shown here.

## Notable Public Functions

- `name()` - returns `Kishu Inu`.
- `symbol()` - returns `KISHU`.
- `decimals()` - returns `9`.
- `totalSupply()` - returns the fixed total supply.
- `balanceOf(address account)` - returns the token balance for an address.
- `transfer(address recipient, uint256 amount)` - transfers tokens.
- `approve(address spender, uint256 amount)` - approves a spender.
- `transferFrom(address sender, address recipient, uint256 amount)` - transfers using an allowance.
- `allowance(address owner, address spender)` - checks allowance.
- `increaseAllowance(address spender, uint256 addedValue)` - increases allowance.
- `decreaseAllowance(address spender, uint256 subtractedValue)` - decreases allowance.
- `isExcluded(address account)` - checks whether an address is excluded from reflection accounting.
- `totalFees()` - returns cumulative reflected fees.
- `reflect(uint256 tAmount)` - lets a non-excluded holder voluntarily reflect an amount from their own balance.
- `reflectionFromToken(uint256 tAmount, bool deductTransferFee)` - converts a token amount into reflected units.
- `tokenFromReflection(uint256 rAmount)` - converts reflected units into token units.

## Review Notes

This breakdown is intended for public understanding, not as a formal audit.

Key things reviewers should verify directly on-chain:

- Current `owner()` address.
- Whether ownership has changed over time.
- Whether any accounts are currently excluded from reflections.
- Current `_maxTxAmount`.
- Transfers involving owner/admin addresses.
- Any relationship between this owner address and other Kishu ecosystem contracts.

Always compare this repository against Etherscan or another trusted Ethereum explorer before relying on it for wallet decisions.
