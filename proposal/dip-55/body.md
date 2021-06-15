# Alternative DIP38: Withdrawal Limit For Creator Rewards Based On Liquidity Pools

This proposal makes up for the shortcomings of DIP38.

The withdrawal limit for creator rewards in DIP38 is tiny. The current geometric mean staking number is about `0.000000000000000009`, so DIP38 had the problem that the withdrawal limit for creator rewards was significantly smaller than expected.

This proposal corrects the withdrawal limit for creator rewards and fluctuates in line with the value of DEV pooled in the liquidity pools and staking flatness.

_You can find the full specifications of this proposal in [DIPs](https://github.com/dev-protocol/DIPs/blob/f34dfaabddaf93497b835a0dbd2b9c60363d83c9/DIPS/dip-55.md)._

## Sentence Summary

This DIP solves the self-staking problem.

## Paragraph Summary

This DIP proposes to set a limit per block on a withdrawable amount for creator rewards. The limit is equal to the withdrawable amount assuming that
_"the value of multiplied the balance of DEV in the liquidity pools of the exchange protocols by the following values; 12, staking flatness, and the value of subtracted the ratio of DEV to ETH in the liquidity pools from 1"_ is staked.

The liquidity pool used as the basis for the calculation will be the DEV:ETH pool on Uniswap, but this selection process can be managed by governance in the future.

- [0x4168CEF0fCa0774176632d86bA26553E3B9cF59d](https://etherscan.io/address/0x4168cef0fca0774176632d86ba26553e3b9cf59d)

## Component Summary

- Set a limit per block on a withdrawable amount for creator rewards.
  - The limit is equal to the withdrawable amount assuming that _"the value of multiplied the balance of DEV in the liquidity pools of the exchange protocols by the following values; 12, staking flatness, and the value of subtracted the ratio of DEV to ETH in the liquidity pools from 1"_ is staked.
  - The staking flatness is the ratio of the geometric mean of staking for all authenticated Properties with 0 as 1 and the arithmetic mean of staking for all authenticated Properties.
  - 1 means 1000000000000000000 in DEV's contract.
  - The limit functions only as like vesting, and there is no change in the total creator rewards for each property.
  - Even if a creator or property holder does self-staking to increase his/her creator rewards, he/she will not be able to get a large amount of creator rewards.
  - An efficient way to increase creator rewards is to increase the limit by staking to someone else's Property instead of self-staking.
  - The limit decreases as the DEV value in the liquidity pools increases and increases as the staking flatness increases.
- The liquidity pool used as the basis for the calculation.
  - The initial liquidity pool will be the [DEV:ETH pool on Uniswap](https://etherscan.io/address/0x4168cef0fca0774176632d86ba26553e3b9cf59d).
  - In the future, governance may allow the selection of liquidity pools.

## Motivation

The act of a creator staking on his Property is defined as "self-staking" here. Self-staking allows creators to earn both staking rewards and creator rewards. Self-staking acts like a tax to stakers, as that is not possible for someone who does not have their own Property. This interferes with the protocol neutrality.

## How winner is decided

The Proposal with the highest number of votes at reaches the closing block will be determined as the winner.

## Development period

The development team plans to complete the development within about a week of the approval of this proposal and then deploy it immediately.

---

# Simulation

## Simulation based on the situation at the time of proposal

| Pooled Token | Balance |
| ------------ | ------- |
| DEV          | 106,506 |
| WETH         | 451     |

The `GM` (geometric mean of staking for all authenticated Properties with 0 as 1) is `1.31063`, the `AM` (arithmetic mean of staking for all authenticated Properties) is `293.09670`. Assume that APY for creators remains unchanged.

**Results**: 2064.09235 DEV per year

**Formula**:

```
T = 106506*(1-(451/106506))*12*1.31063/293.09670 = 5690.90807
ANNUAL_L = 5690.90807*0.3627 = 2064.09235
```

## If DEV value is high

| Pooled Token | Balance |
| ------------ | ------- |
| DEV          | 58,000  |
| WETH         | 1200    |

Assume that GM, AM, and APY for creators remain unchanged.

**Results**: 1105.46835 DEV per year

**Formula**:

```
T = 58000*(1-(1200/58000))*12*1.31063/293.09670 = 3047.88627
L = 3047.88627*0.3627 = 1105.46835
```

## Further, if staking flatness is high

| Pooled Token | Balance |
| ------------ | ------- |
| DEV          | 58,000  |
| WETH         | 1200    |

The `GM` (geometric mean of staking for all authenticated Properties with 0 as 1) is `2.5`, the `AM` (arithmetic mean of staking for all authenticated Properties) is `293.09670`. Assume that APY for creators remains unchanged.

**Results**: 2108.65833 DEV per year

**Formula**:

```
T = 58000*(1-(1200/58000))*12*2.5/293.09670 = 5813.78091
L = 5813.78091*0.3627 = 2108.65833
```
