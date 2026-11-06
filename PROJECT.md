# Gatherport: product overview

## Purpose

Gatherport is an independent wallet utility in development. Its intended purpose is to help people review selected Ethereum token balances and consolidate eligible assets into USDC in the same wallet, with a clear explanation of output, costs and permissions before they decide to proceed.

## The problem

A wallet can accumulate balances across several tokens. Deciding what to keep, what to consolidate and whether the conversion is worth its costs can require several separate steps. Gatherport brings those decisions into one focused review experience.

## Initial scope

- Ethereum as the initial network.
- USDC as the initial destination asset.
- Explicit selection of source tokens and amounts.
- A consolidated review of output, costs and required permissions.
- Wallet-owner confirmation for any future live execution.

Cross-chain bridging, automatic trading, custody, deposits, yield strategies and portfolio recommendations are outside the initial scope.

## Intended live journey

1. Connect a supported wallet and read eligible balances.
2. Select tokens and amounts to consolidate.
3. Obtain and validate a current quote.
4. Review expected output, price impact where available, fees and separate network costs.
5. Review any necessary token approvals and the transaction request.
6. Confirm through the connected wallet.
7. View submission, confirmation or failure status.

These steps describe the intended product, not functionality already available in the current demo. A consolidated swap can still require separate approval transactions. Small balances may not be economical to consolidate, and not every token will have a usable route.

## What the current release implements

The public release contains a responsive English website, an interactive sample wallet, input validation, illustrative consolidation math, a review dialog, a completion walkthrough and original project assets.

The sample balances, prices, allowances and costs are fixed fixtures. Changing a value affects the local demonstration only. No wallet access, live quote request, permission approval or transaction submission is implemented.

## Product principles

**Clarity before action.** Put the output, costs and permission requests in one understandable review.

**Deliberate selection.** Do not select or trade assets on behalf of the user without an explicit decision.

**Visible boundaries.** Label unavailable routes, expired quotes and unsupported assets instead of silently substituting a different trade.

**Control stays with the wallet owner.** A future live release must obtain the user's approval through their own wallet.

## Implementation direction

The demonstration is a dependency-free static website. A live implementation would require wallet integration, current token metadata, a server-side quoting component, route and spender validation, allowance handling, transaction simulation and outcome tracking.

Use token integer units and appropriate fixed-point arithmetic for a live release. Demo floating-point calculations are not settlement logic. Validate chain, token addresses, amounts, recipient, spender, quote expiry and transaction calldata before requesting any signature.

Secrets belong on a controlled server, never in the public website or repository. A live deployment also needs a hosting arrangement suitable for transactional software, documented operational responsibilities and its own security review.

## Development stages

1. **Interactive experience:** available in the current repository.
2. **Live pricing and eligibility:** planned.
3. **Wallet execution:** planned.
4. **Production validation:** planned, after the previous stages work end to end.

No production launch date or current live trading capability is claimed.
