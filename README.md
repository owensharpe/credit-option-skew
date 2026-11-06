# Does Credit Option Skew Predict Spread Widening?

I'm building a credit analytics engine and using it to test whether skew in credit ETF options predicts spread widening once you strip out the part of skew that comes mechanically from measuring in price instead of spread. Credit ETF options are quoted on price, but credit risk lives in spreads, and the mapping between the two is nonlinear, so some of the skew you see is just that translation. The question is whether what's left over carries real information about where spreads go next.

**Status:** In progress. The engine lives in its own repo, [credit-engine](https://github.com/owensharpe/credit-engine). This repo holds the paper's measures and tests, which sit on top of it.

**Next:**

- Finish the engine
- Separate the mechanical part of skew from the rest
- Test the residual against future spread changes

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
