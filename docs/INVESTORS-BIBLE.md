# Investor's Bible

The Investor's Bible is the long-horizon reading path in RawMarkets. Its page contains ten laws, a reader-controlled pin list, advisory reference cards, and a ten-question self-assessment.

## The ten laws in the current interface

| Law | Topic |
| --- | --- |
| I | Maintain sovereign liquidity. |
| II | Honor cumulative compound growth. |
| III | Distrust the daily hype machine. |
| IV | Separate exposure across asset groups. |
| V | Systematize dollar-cost averaging. |
| VI | Reduce recurring fees and expenses. |
| VII | Set a minimum holding horizon. |
| VIII | Invest in businesses and assets the reader understands. |
| IX | Treat precious metals as a hedge, not a yield-producing asset. |
| X | Use written limits to manage fear and greed. |

These are editorial principles shown in the page. They are not an execution engine and do not control brokerage activity.

## Self-assessment flow

1. The reader toggles ten yes-or-no statements.
2. **Evaluate Adherence Score** counts the `true` answers.
3. The displayed Survivability Index is `yes answers × 10%`.
4. The page groups results into three text bands: 0 to 4, 5 to 7, and 8 to 10 affirmative answers.

Answers, score, and pinned laws are held in the page's component state. The current implementation does not persist those answers to the RawMarkets database.

## Wording difference to reconcile

The Law VII description says a reader should be prepared to hold an equity for five years. Its diagnostic question says three or more years. The current product source contains both thresholds. This companion documents that discrepancy so the language can be aligned in a later product update.

## Code

The page content and scoring are in [`InvestorsBible.tsx`](https://github.com/RawPowered/RawMarkets/blob/main/src/components/InvestorsBible.tsx). The page defines this canon separately from the shared `wealthBibleRules.ts` catalog.

## Interpretation limits

The score measures agreement with self-reported prompts. It does not inspect holdings, cash balances, risk exposure, trading history, tax position, or asset quality. A higher score is not evidence that a portfolio is safer or more likely to perform well.
