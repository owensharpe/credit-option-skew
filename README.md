# Does Credit Option Skew Predict Spread Widening?

Does skew in credit ETF options predict spread widening once you strip out the part that comes purely from measuring in price instead of spread? Credit ETF options are quoted on price, but credit risk lives in spreads. Spreads tend to move in proportion to their level, and prices fall when spreads rise, so even a smile that’s flat in spread terms shows up as put skew in price terms. Some of the skew you see is just that translation. The question is whether what’s left over carries real information about where spreads go next.

**Status:** In progress. The analytics engine lives in its own repo, [credit-engine](https://github.com/owensharpe/credit-engine), and is shared with another paper. This repo holds the paper's measures and tests, which sit on top of it.

**Next:**

- Finish the engine core: OIS curve, CDX pricing, price-to-spread mapping
- Measure how much price-space skew is mechanical, using simulated spread paths
- Test what’s left against future spread changes

## Data

All the data comes from Bloomberg and isn't included here, because Bloomberg data can't be redistributed. The [credit-engine README](https://github.com/owensharpe/credit-engine#data) lists every ticker and field and explains how to rebuild the files.

## Setup

Clone both repos side by side and install them together:

```bash
git clone https://github.com/owensharpe/credit-engine
git clone https://github.com/owensharpe/credit-option-skew
pip install -e ./credit-engine -e "./credit-option-skew[dev]"
```

Point `CREDIT_ENGINE_DATA` at the folder holding the Bloomberg pulls.
