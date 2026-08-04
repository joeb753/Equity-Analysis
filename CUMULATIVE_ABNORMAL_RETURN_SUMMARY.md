# Cumulative Abnormal Return Meathod

## What model this analysis uses

This project uses the **market model**, the standard approach in academic and professional event-study finance for measuring how much a stock's return deviates from what would normally be expected.

The market model estimates a stock's "normal" return using a simple linear regression against a benchmark (in this case, oil or the XLE energy sector ETF, run as two separate single-factor models):

```
expected return = alpha + beta × (benchmark return)
```

- **Alpha** is the stock's average daily return that isn't explained by the benchmark — its normal day-to-day drift, independent of oil or sector movement.
- **Beta** measures how sensitive the stock normally is to the benchmark — how much it tends to move for every 1% the benchmark moves.

Both alpha and beta are estimated using an **estimation window** — a stretch of trading days *before* the event being studied (in this case, before the war started on Feb 28, 2026). This ensures the "normal" relationship is based on how the stock behaved under ordinary conditions, not conditions already affected by the event itself.

## How abnormal return (AR) is calculated

Once alpha and beta are estimated from the clean pre-war window, they're used to calculate what the stock's return *should have been* on any given day, based purely on how the benchmark moved that day:

```
predicted return (that day) = alpha + beta × (benchmark's actual return that day)
```

The **abnormal return** for that day is simply the difference between what actually happened and what was predicted:

```
AR = actual return − predicted return
```

A positive AR means the stock did better than its normal relationship to the benchmark would suggest. A negative AR means it did worse.

## How cumulative abnormal return (CAR) is calculated

CAR is the sum of daily abnormal returns across a defined window of time:

```
CAR = sum of AR across every day in the window
```

In this analysis, CAR is calculated over the full war period (Feb 28 – Jun 30, 2026), giving one number per stock that represents its total, cumulative over/underperformance relative to what its normal pre-war relationship to oil (or XLE) would have predicted.

## Why this model, specifically

The market model is the standard choice in event-study research because it accounts for a stock's individual sensitivity to a benchmark, rather than assuming every stock should move identically to it. This is considered more rigorous than simpler alternatives, such as assuming a flat beta of 1 for every stock or ignoring the benchmark entirely and just using a stock's own historical average return.

## Sources

- MacKinlay, A.C. (1997). "Event Studies in Economics and Finance." *Journal of Economic Literature*, 35(1), 13-39. — the standard reference establishing the market-model event-study methodology used here.
- Campbell, J.Y., Lo, A.W., & MacKinlay, A.C. (1997). *The Econometrics of Financial Markets*. Princeton University Press. — foundational text on abnormal return and CAR calculation.
- Brown, S.J. & Warner, J.B. (1980, 1985). "Measuring Security Price Performance" and "Using Daily Stock Returns: The Case of Event Studies." *Journal of Financial Economics*. — established the statistical properties of the market model for daily-return event studies.
- EventStudyTools, "Expected Return Models for Event Studies." https://www.eventstudytools.com/expected-return-models — plain-language comparison of the market model against simpler alternatives (market-adjusted, constant mean return models).
- "Event Studies," Chapter 39 in *A Guide on Data Analysis*. https://bookdown.org/mike/data_analysis/sec-event-studies.html — overview of abnormal return mechanics and the assumptions required for a valid event study.
