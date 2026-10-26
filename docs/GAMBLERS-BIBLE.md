# Gambler's Bible

The Gambler's Bible presents a high-risk decision framework. Its purpose in the interface is to make sizing, survival, exit discipline, and common behavioral failures visible before a reader evaluates speculative risk.

## What the page presents

- **Ten commandments:** expected value, Kelly sizing, cutting losers, bounded winner exposure, herd behavior, capital preservation, process quality, macro context, drawdown discipline, and liquidity.
- **Ten trading sins:** revenge trading, over-leverage, thesis attachment, ignoring costs, emotional sizing, averaging down, boredom trading, mistaking luck for skill, FOMO entries, and entering without an exit plan.
- **A six-step quantitative protocol:** gather a sufficiently large sample, estimate payoff and win probability, calculate Kelly, cap the fraction, rebalance, then pause and recalibrate at a drawdown threshold.
- **A ten-answer discipline diagnostic:** the interface counts affirmative answers and shows `yes answers × 10%` as its Survivability Index.

## The protocol, as represented in code

The page's static protocol text specifies:

1. Extract performance metrics from at least 100 trials.
2. Estimate payoff ratio `b = average win / average loss`.
3. Calculate Kelly fraction `f* = (b × p − q) / b`, where `p` is win probability and `q = 1 − p`.
4. Use a quarter-Kelly cap in the protocol text.
5. Apply continuous 50/50 rebalancing.
6. Pause and recalibrate after a drawdown threshold is reached.

The current page displays these instructions. It does not ingest 100 trades, calculate the user's Kelly fraction, enforce position sizes, rebalance a portfolio, or pause live orders.

## Scoring bands

The 10 self-reported answers produce a 0 to 100 score in ten-point increments. The screen labels 0 to 4 as **Ruin-Zone Exposure**, 5 to 7 as **Developing Edge**, and 8 to 10 as **Elite Quant Tier**. These names are product copy, not independently validated risk classifications.

Answers, score, and pinned commandments live in component state. The current page does not persist them to the database.

## Kelly wording differs across the product

The Gambler's protocol describes a quarter-Kelly cap. The shared Wealth Bible Investor Pillar C describes Half Kelly. The two pages therefore express different sizing conventions. They should be read as separate educational statements until the product owner reconciles them.

## Code

The commandments, sins, protocol, diagnostic prompts, and score thresholds are in [`GamblersBible.tsx`](https://github.com/RawPowered/RawMarkets/blob/main/src/components/GamblersBible.tsx). It is separate page content, not the shared Wealth Bible rule catalog.

## Risk boundary

The page is an educational reflection tool. It does not provide a validated trading system, individualized investment guidance, or broker execution. Expected value and Kelly estimates require reliable inputs and assumptions that this screen does not collect or verify.
