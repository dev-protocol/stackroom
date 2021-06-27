# Short term liquidity program

As we all know, improving liquidity is a long-term challenge for Dev Protocol.

We already offer the Uniswap v2 liquidity program utilizing the forked Geyser, but the existing program will end on July 3. I plan the next completely revamped liquidity program, but I still need some time to establish the details.

Before establishing the details of the long-term liquidity program details, I propose a short-term program by a new Geyser. This proposal avoids creating gaps in liquidity programs and allows the community to devote sufficient time to new liquidity programs.

## What is a new Geyser?

Deploy the same new one as the existing Geyser contract. The new Geyser offers a mechanism similar to the existing Geyser but with liquidity rewards in a completely flat state. As a result, new liquidity providers and existing liquidity providers can participate in the program under the same conditions.

We recommend that existing liquidity providers unstake LP tokens from the existing Geyser and stake them into the new Geyser. The reward multiplier in the existing Geyser will be reset in the new Geyser. However, keep in mind that when you (an existing liquidity provider) reach 5x again in the new Geyser, all past rewards in the new Geyser will also be 5x. This means that if an existing liquidity provider stakes in the new Geyser for more than a month, that liquidity provider will not lose its reward multiplier.

## Duration and rewards

I propose the duration and liquidity rewards as follows:

- Duration: **2 months**
- Liquidity rewards: **10,000 DEV** (However, if the liquidity increases by 20% or more, add **8,000 DEV** to avoid low APY)
- Bonus Period: **1 month**
- Max Reward Multiplier: **5x**

### APY simulation:

| Liquidity increments | Expected max APY |
| -------------------- | ---------------- |
| 1%                   | 634.73%          |
| 2%                   | 317.36%          |
| 3%                   | 211.58%          |
| 5%                   | 126.95%          |
| 8%                   | 79.34%           |
| 13%                  | 48.83%           |
| 21%                  | 30.23%           |

## Start date

The new Geyser will start on July 2, 2021, at 9:00 in UTC.

Existing liquidity providers can maximize their rewards on their existing Geyser by waiting until July 3, when the existing Geyser ends, and then migrating their LP tokens.

## Discussions

Discussions about this proposal can be started in [this post in the forum](https://community.devprotocol.xyz/t/short-term-liquidity-program/277).
