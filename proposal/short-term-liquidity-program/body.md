# Short term liquidity program

As we all know, improving liquidity is a long-term challenge for Dev Protocol.
We already offer the Uniswap v2 liquidity program utilizing the forked Geyser, but the existing program will end on July 3. I plan the next completely revamped liquidity program, but I still need some time to establish the details.

Before establishing the details of the long-term liquidity program details, I propose two short-term programs, an "extended Geyser" or a "new Geyser." This proposal avoids creating gaps in liquidity programs and allows the community to devote sufficient time to new liquidity programs.

## What is an extended Geyser?

Add liquidity rewards to the current Geyser contract. Existing liquidity providers will earn additional liquidity rewards while preserving their current Reward Multiplier. Most of the added liquidity rewards will be allocated to existing liquidity providers, as many liquidity providers already have a time factor of around 3-6 months. Therefore, there are barriers to entry for new liquidity providers.

## What is a new Geyser?

Deploy a new one that is the same as the existing Geyser contract. The new Geyser provides a mechanism similar to the existing Geyser, but the liquidity rewards are provided in a completely flat state. New liquidity providers and existing liquidity providers can participate in the program under the same conditions.

## Duration and rewards

Whether we choose the "extended Geyser" or the "new Geyser," I propose the duration and liquidity rewards as follows:

- Duration: **2 months**
- Liquidity rewards: **10000 DEV (However, if the liquidity increases by 20% or more, add 8000 DEV to avoid low APY)**

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

_\*These APYs are the added liquidity divided by the added total liquidity rewards. In the case of the extended Geyser, the existing states are also considered, so these APYs do not show an exact value._
