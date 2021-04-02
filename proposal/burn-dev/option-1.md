## Proposal One: Burn 3.5M DEV Tokens

Burn 3.5 Million DEV tokens. As the aggregate supply decreases with the burn, the staking rate increases relatively, and the inflation rate and staking APY decrease. Therefore, we'll update the Policy contract to match the APY to the current APY. This will involve updating the variable of the current Policy contract 0.00012 DEV per block to 0.000132 DEV per block (inflation per Creator).

### Proposal One: Overview

| Current Supply                 | 12,792,742 |
| ------------------------------ | ---------- |
| Current Distributable Supply   | 11,799,473 |
| Burn Amount                    | 3,500,000  |
| Already Distributed            | 1,109,860  |
| Post-Burn Distributable Supply | 8,299,473  |
| Post-Burn Total Supply         | 9,409,333  |

### Proposal One: DEV Distribution

![Proposal One: DEV Distribution](https://raw.githubusercontent.com/dev-protocol/stackroom/proposal-burn-dev/proposal/burn-dev/asset/proposal-one-dev-distribution.svg?sanitize=true)

### Proposal One: Effects on Stakes.Social

| Current Creator APY   | 38.60%  |
| --------------------- | ------- |
| Current Patron APY    | 37.08%  |
| Current ASG           | 2.44%   |
| Post-Burn Creator APY | 38.52%  |
| Post-Burn Patron APY  | 37.01%  |
| Post-Burn ASG         | 3.3543% |
