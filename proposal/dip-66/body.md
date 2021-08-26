# DIP-66: sTokens, NFTs mirroring DEV staking

sTokens are NFTs and stored unique status for each staking position. Transferring sTokens means transferring the staking itself.

sTokens extends staking composability and brings the following use cases to Dev Protocol:

- Creators offer perks to specific sTokens holders
- Create multiple staking positions as multiple sTokens for one Property token (a.k.a. Creator tokens)
- Sale of sTokens by early staking users
- Borrowing any tokens with sTokens as collateral
- Further expansion of composability with a contract that bridges sTokens that meet certain conditions to ERC-20 tokens

_You can find the full specifications of this proposal in [DIPs](https://github.com/dev-protocol/DIPs/blob/6b242b118f872b160bf53284f6730a9be6d0be0e/DIPS/dip-66.md)._

## References

- [[RFC] sTokens, a token mirroring DEV staking](https://community.devprotocol.xyz/t/rfc-stokens-a-token-mirroring-dev-staking/303/)
- [DIP: sTokens, NFTs mirroring DEV staking](https://github.com/dev-protocol/DIPs/pull/66)

## Sentence Summary

A proposal for ERC-721 tokens mirroring DEV staking, called sTokens.

## Paragraph Summary

Users earn NFTs called sTokens, by staking DEV tokens.

sTokens stores the state of the staking.

sTokens improves staking composability.

## Component Summary

- **[Uniqueness]**
  sTokens is a unique NFT for each staking.
- **[Certificate of Staking]**
  A sTokens holder is considered to be the person who ran the staking stored in sTokens. If you transfer sTokens to another person, that right will also be transferred.

  sTokens stores the values of staking destination, staking amount, last reward unit price, cumulative reward amount, and pending reward amount into each NFT.

- **[NFT, not ERC-20]**
  By staking 10 DEV on a Property token, the staker gets 1 sTokens NFT. By staking 1,000 DEV on a Property token, the staker gets 1 sTokens NFT.
- **[Update]**
  sTokens change the state by withdrawing or adding staking. There is no burn.
- **[Bridge]**
  In some cases, ERC-20 is preferable to NFT. In that case, a user can extend the composability by creating a third-party bridge contract for NFT<>ERC-20.

## Motivation

DEV staking users can prove that they are staking by the function in the Lockup contract on Dev Protocol. However, the function is not a standardized interface such as ERC-721 or ERC-20, which creates an inconvenient situation for composability.

## Specification

sTokens are automatically issued upon staking and can be updated upon unstake.

- **[Creating sTokens]**
  sTokens is created as an NFT by STokensManager when users call `Lockup.deposit` and the Lockup contract calls STokensManager.
- **[Updating sTokens]**
  By users call the `Lockup.deposit` or `Lockup.withdraw`, STokensManager is called from the Lockup contract, data of existing sTokens will be updated by STokensManager.
- **[Deleting sTokens]**
  There is no deletions interface in sTokens. By the same procedure as updating sTokens, the amount of staking position is set to 0 to indicate that the position no longer exists.
- **[STokensManager]**
  A new contract to manage minting and updating sTokens, the deployed address by the local variables of Lockup Contract have been retained.

### Why not ERC-20?

Dev Protocol staking rewards change the rate of return at unpredictable timings as third parties increase or decrease staking. To implement that property, Dev Protocol handles a cumulative sum of the reward unit prices that continue to be increased and a snapshot of that cumulative sum at the time for each staking. The staking rewards are unique, and fungible tokens are inconvenient to retain that unique data. This is similar to why Uniswap v3's liquidity tokens are now NFTs instead of ERC-20.

## Development period

The development team plans to complete the development within about a few weeks of the approval of this proposal and then deploy it immediately.

---

_You can find the full specifications of this proposal in [DIPs](https://github.com/dev-protocol/DIPs/blob/6b242b118f872b160bf53284f6730a9be6d0be0e/DIPS/dip-66.md)._
