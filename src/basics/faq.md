---
icon: ":question:"
---

# FAQ

## How do I modify my position size?

Currently Hyperyield does not support adding to or removing liquidity from an open position.

If you want to increase your position size you can deposit more HYPE to your Hyperyield wallet at any time and wait for a rebalance (it will automatically be included then) or manually close and reopen your position.

If you want to decrease your position size you will have to close your position and withdraw the funds to another wallet before re-opening a position.

## How do I withdraw funds?

Users can withdraw funds at any time from Hyperyield.

!!!danger
Be careful withdrawing HYPE if you have an open position. Doing so may cause your account to have insufficient funds for gas and Hyperyield will be unable to manage your position for you.
!!!

To withdraw funds:

1. Click the wallet dropdown and go to Account.
2. Next to the asset you want to withdraw, click the Withdraw button.
3. Enter the recipient address and how much you want to withdraw.
4. Click the Withdraw button and your funds will be sent immediately.

## How do I export my private key?

Because Hyperyield is a self-custodial solution you can always export your private key into a wallet of your choice. Hyperyield never sees your private key at any point in time.

That said, keep in mind that Hyperyield, by necessity, is an additional signer on your provisioned wallet and can perform actions limited in scope to what is necessary to manage a liquidity position. It is strongly discouraged for users to use their Hyperyield wallet for anything outside of normal Hyperyield operations.

If you want to export your private key:

1. Click the wallet dropdown and go to Account.
2. Click the Export private key button and follow the instructions.

## Why does Hyperyield only allow 1 position at a time?

For now, this significantly simplifies the service so we only have to consider the entire wallet balance on every rebalance. We plan to allow multiple pools and let you to customize the amount of funds to allocate to each in the future.