# Energy Sector Analysis During The Iran War

An event-study analysis of five major energy companies with diverse Middle East exposure, examining how they fared during the 2026 Iran war compared to the sector as a whole.

## Executive Summary

This project tests how five major energy companies with diverse Middle East exposure fared during the 2026 Iran war compared to the sector as a whole. Cumulative Abnormal Return, or CAR, is used throughout to measure how far each company's actual performance diverged from what would normally be expected given its historical relationship to the sector.

Measured against their own sector peers, the five companies told different stories. ConocoPhillips and BP both outperformed, likely reflecting their heavier concentration in stable, lower risk regions. ConocoPhillips draws much of its output from US shale, while BP, despite its historic Middle East ties, holds substantial UK and North Sea assets that were largely insulated from the conflict. Chevron and Shell both tracked the sector closely, suggesting their mix of exposure was fairly typical and didn't set them apart in either direction. ExxonMobil stood apart as the clearest underperformer, even relative to its own peers, pointing to something particular about the company itself rather than a sector-wide effect. The most likely explanation is its deep and integrated operations across the Middle East, which left it more directly exposed to the war's disruptions. Overall, the data collected is highly revealing, and it shows BP and ConocoPhillips as clear winners should a more drawn out conflict in the Middle East continue.

## Study Design

- **Companies studied:** ExxonMobil (`XOM`), Chevron (`CVX`), ConocoPhillips (`COP`), BP (`BP`), Shell (`SHEL`)
- **Benchmark:** the Energy Select Sector SPDR ETF (`XLE`)
- **Data window:** daily closing prices, January 2025 – June 2026
- **Pre-war baseline period:** roughly 270 trading days before the war began, through Feb 1, 2026, used to establish each company's normal relationship to the sector before any war-related effects
- **War period measured:** Feb 20, 2026 – Jun 25, 2026
- **Key dates in this period:** Feb 28, Mar 6, Apr 8, May 20, and Jun 16, 2026

## Methodology

**Data:** Daily close prices for the Energy Select Sector SPDR ETF (`XLE`) and five major energy companies, pulled via `yfinance`.

**Approach:** a market-model event study, using a single-factor model against XLE. The model estimates each company's normal relationship to the sector on a roughly 13-month pre-war window, then measures the cumulative gap between actual and predicted performance across the full war period.

**War time-frame:** the roughly 4-month period measured, Feb 20 through Jun 25, 2026, was chosen to capture the full arc of the conflict, from its outbreak through the escalation and de-escalation that followed, ending shortly after the peace framework was signed. Within this window, 5 key dates were identified that caused oil and energy sector shocks:

- Feb 28, 2026, US and Israel launch war on Iran
- Mar 6, 2026, export halt fails to resolve, grace period ends
- Apr 8, 2026, 8-day ceasefire announced
- May 20, 2026, talks in "final stages," strikes called off
- Jun 16, 2026, peace framework signed at G7, Strait of Hormuz to fully reopen

## Key Findings

**1. Chevron and Shell tracked the sector closely during this period.**
Chevron's steady performance likely reflects its genuinely limited exposure to the region. HSBC noted that Chevron's Middle East production totals less than 200,000 barrels per day, compared to more than 900,000 barrels per day for a more exposed rival, and Chevron's own CEO put the region at roughly 5% of total output. Chevron still held real, if smaller, interests there, including a temporary curtailment at its Leviathan gas field in Israel.

Shell also tracked the sector closely, but its case is more interesting, because its production exposure to the Middle East was not actually small. Analysts estimated the region accounted for roughly 20% of the company's output, with Qatar alone making up about 10%. What kept Shell from falling was its trading arm. As Middle East disruptions cut into gas production from Qatar, Shell's trading and optimization business benefited directly from the resulting price volatility, with the company explicitly citing stronger trading results as a meaningful offset to the production losses.

**2. ExxonMobil is the standout underperformer.**
ExxonMobil is the standout underperformer among the five. The company's Middle East footprint is among the largest of any major oil company, representing roughly 20% of total output, spanning integrated operations across the UAE, Qatar, and Saudi Arabia that had long been core to its business. The war cut deeply into that footprint, shaving 6% off first quarter production, and pushed net income to a five year low of $4.2 billion, driven partly by a $706 million loss tied specifically to the conflict. Exxon absorbed a real financial hit in close proportion to how exposed it actually was to the region. That connection between the depth of Exxon's footprint and the depth of its underperformance also helps explain why it lagged even relative to companies like Chevron and Shell, which carried real Middle East exposure of their own but never approached Exxon's scale of integration in the region. Where those companies were able to absorb the shock through limited exposure or offsetting trading gains, Exxon had neither cushion available to the same degree, and its results and stock performance reflected that difference directly.

**3. ConocoPhillips and BP's outperformance likely reflects their geographic footprint.**
The two companies got there in different ways. ConocoPhillips is overwhelmingly a domestic producer, with the bulk of its output coming from US shale plays like the Permian and Eagle Ford rather than from anywhere near the Strait of Hormuz. That footprint meant the company had little direct production to lose when the war broke out, and its shares rallied on the same days that oil prices spiked, since rising prices lifted its business without the accompanying regional risk that weighed on more exposed peers.

BP's path to outperformance looked different. The company still carries real Middle East exposure of its own, so its gains cannot be explained by insulation in the same way ConocoPhillips's can. Instead, BP's large oil trading and marketing business appears to have found opportunity in the very volatility the war created, turning sharp price swings into a source of profit rather than simply absorbing them as risk. Beyond the immediate trading gains, recent comments from President Trump calling on the UK to expand North Sea oil operations could give BP even greater insulation from Middle East instability in the future.

## Limitations

- **n=5 companies**, chosen deliberately to represent a range of Middle East exposure and geographic strategy. Each company's result is best read as its own case study rather than as part of a broader statistical sample.
- **XLE is not a fully independent benchmark for XOM, CVX, and COP,** since all three are themselves XLE holdings, with XOM and CVX its two largest positions. BP and Shell, as non-S&P-500 companies, are not XLE constituents and offer a more independent comparison point.
- **The war period measured, Feb 20 through Jun 25, 2026, captures the conflict's most optimistic stretch,** including the June 16 peace framework signing, ahead of the ceasefire's later collapse in July 2026. The patterns identified here reflect that specific window in the conflict.
- **Future extensions of this project could formally test for structural breaks** in each company's relationship to the sector, using tools like Chow tests or dummy-interaction regressions, and could incorporate professional-grade financial data alongside `yfinance`.

## Sources

- HSBC's Chevron/Exxon Middle East exposure comparison: [CNBC, March 20, 2026](https://www.cnbc.com/2026/03/20/buy-chevron-as-its-middle-east-exposure-is-lower-than-rival-exxons-says-hsbc.html)
- Chevron CEO's 5% Middle East output figure: [Reuters/BOE Report, June 12, 2026](https://boereport.com/2026/06/12/chevron-continues-to-look-at-new-opportunities-in-middle-east-ceo-says/amp/)
- Shell's Q1 2026 earnings driven by trading amid Middle East disruption: [Yahoo Finance, May 11, 2026](https://finance.yahoo.com/markets/stocks/articles/shell-post-q1-earnings-stock-151500297.html)
- Shell's Q2 2026 trading gains offsetting production shortfalls: [Kalkine, 2026](https://kalkine.co.uk/news/announcements/shell-updates-second-quarter-2026-outlook-amid-middle-east-conflict-impact)
- ExxonMobil's Q1 2026 earnings and Middle East exposure: [Yahoo Finance, May 1, 2026](https://finance.yahoo.com/sectors/energy/articles/exxonmobil-q1-2026-earnings-beat-114559774.html)
- ConocoPhillips' US-focused footprint and share rally: [The Motley Fool/AOL, 2026](https://www.aol.com/articles/why-conocophillips-rallied-today-205402878.html)
- BP's profit doubling on trading gains: [Yahoo Finance UK, April 28, 2026](https://uk.finance.yahoo.com/news/iran-war-boosted-profits-bp-133511491.html)

## Tools

Python, pandas, numpy, Yahoo Finance
