---
icon: ":gear:"
order: 10
---
# How it works

## Provisioned wallets

Hyperyield uses Privy as its wallet provider. All users that log into Hyperyield are provisioned a wallet. Due to how Hyperyield works, users must use this managed wallet and not their own.

Before entering a position, Hyperyield will add itself as a signer to the wallet the user is provisioned. This is necessary for Hyperyield to be able to manage their position on their behalf. Hyperyield uses policies in Privy to restrict what actions it can take with the user's wallet so that it can only interact with the exchange pools and [LiquidSwap](https://liqd.ag), our swap provider.

## Auto-swapping

In order to make Hyperyield as simple as possible, it handles all token swapping on the user's behalf. This includes:

- Automatically wrapping HYPE to WHYPE
- Swapping WHYPE to the two tokens in a pool and vice versa
- Swapping from one pool token to the other when rebalancing
- Automatically unwrapping WHYPE in order to maintain a minimum balance for gas
- Swapping to feUSD for deposits into Felix stability pools

This means that the user only ever has to worry about depositing HYPE into their Hyperyield account.

## Position management

Hyperyield's backend constantly monitors all open positions to check and see if they are still in range. This check occurs roughly once per minute. If the position falls out of range, it will:

1. Close the existing position and mark it as "rebalanced". This collects all fees and all collateral in the position.
2. Check the wallet's current HYPE balance. If it is below the threshold reserved for gas (currently 0.1 HYPE), it will automatically swap an available token back to HYPE (up to 0.2 HYPE). If it's above the upper gas threshold of 0.2 HYPE, it will auto-wrap the excess HYPE to WHYPE and then swap the WHYPE to the first token in the pool.
3. Calculate, based on the user's current token balances, how much is required of each token to re-enter the pool and perform the swap from one pool token to the other. Please note that sometimes there will be leftover collateral due to pool tick spacing and price movement that can happen during the rebalance procedure.
4. Re-enter the pool with the maximum amount of capital possible.

## Closing a position

A user can always manually close a position at any time. Doing so will tell Hyperyield to perform the following steps:

1. Close the position and claim all collateral and fees accrued. This marks the position as "closed".
2. Swap the full token balances for each token received back from the closed position to WHYPE.

## Yield strategies

Hyperyield offers the ability to take additional actions with the yield generated once a position is rebalanced or closed. By default, Hyperyield will reinvest all earned yield into the next position. However, you can change this strategy on your Account page.

At this point in time, the only other supported yield strategy is depositing into [Felix stability pools](https://usefelix.gitbook.io/docs/money-market-products/quickstart/earning-feusd-yield). When a position is closed, Hyperyield will:

1. Swap all earned yield to feUSD.
2. Deposit the feUSD into the stability pool of your choice.

You can view your stability pool balance on your Account page at any time. You can also withdraw from the stability pool. When doing so, you will receive feUSD back in your Hyperyield account along with any other assets earned from the stability pool.