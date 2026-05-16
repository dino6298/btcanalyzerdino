# Dino Futures Tool V3 Official

A lightweight HTML-only crypto futures decision-support dashboard for market analysis, opportunity scanning, backtesting, forward testing and risk management.

> Built for manual trading decision support.  
> This tool does not place orders automatically.

---

## Live Demo

[https://dino6298.github.io/btcanalyzer/](https://dino6298.github.io/btcanalyzerdino/)

---

## Overview

**Dino Futures Tool V3 Official** helps analyze crypto futures setups using multiple layers of confirmation, risk filtering and execution tracking.

The goal is not to generate random buy/sell signals, but to help filter out low-quality trades and support disciplined manual execution.

The tool is designed for:

- Crypto futures market analysis
- Opportunity scanning
- Entry Zone planning
- Risk management
- Backtesting
- Forward testing
- Manual trade decision support

---

## Key Features

### Trade Plan Engine

The tool generates a structured trade plan with:

- LONG / SHORT setup detection
- Entry Zone instead of a single fixed entry price
- Entry Price
- TP1 / TP2
- Stop Loss
- Entry Timing
- Signal Stage
- Risk Quality
- No Trade Guard
- Net RR after fee and slippage

Supported signal stages:

```text
SETUP_FORMING
WAIT_PULLBACK
ENTRY_ZONE
TRIGGER_READY
STALE_PLAN
MANUAL_ACTIVE
```

---

### Playbook Engine

V3 Official includes a Playbook Engine that classifies each setup into a more specific trade idea.

Supported playbooks:

```text
FVG Continuation
Trend Pullback
Liquidity Sweep Reversal
Breakout Retest
Range Mean Reversion
General Momentum
```

Each playbook includes:

- Playbook name
- Playbook confidence
- Playbook rule/reason
- Setup type
- Market context

---

### No Trade Guard

The No Trade Guard helps block low-quality or risky setups.

It can block a trade when:

- Entry is too far
- Entry Timing is too low
- Real RR is too low
- Net RR after fee/slippage is too low
- Stop Loss is too wide
- Market is too chaotic
- Setup is stale
- Trade already reached TP/SL
- Daily Risk Guard is triggered

Risk modes:

```text
Safe
Balanced
Aggressive
```

---

### Risk Quality Score

The Risk Quality Score gives a quick view of trade quality.

It evaluates:

- Entry distance
- Entry Timing
- RR
- Net RR
- SL width
- Market regime
- Signal stage
- Setup rank

Displayed as:

```text
Risk Quality: 0–100
```

---

### Daily Risk Guard

Daily Risk Guard helps prevent overtrading.

Default rules:

```text
Max trades per day: 5
Max daily loss: -3R
Max consecutive losses: 2
```

Daily status is displayed on the top bar:

```text
Daily: 2/5 · -0.80R · OK
```

---

### Position Sizing

The tool includes position sizing based on:

- Account size
- Risk %
- Leverage
- Margin mode
- Fee %
- Slippage %
- Net RR

Outputs:

- Margin
- Risk USDT
- Position size
- Quantity
- Net RR
- Binance Rule status

---

### Binance Futures Rule Validation

The tool reads Binance Futures exchange rules using public market data.

It validates:

- Tick size
- Step size
- Minimum quantity
- Minimum notional
- Price precision
- Quantity precision

This helps make sure copied prices and quantities are closer to Binance Futures requirements.

---

### Opportunity Scanner

The scanner helps find trade candidates across top symbols.

Supported scanner range:

```text
Top 10
Top 20
Top 25
```

Scanner logic:

```text
Lite Scan
→ Deep Scan best candidates
→ EV Score ranking
→ Filter results
```

Scanner filters:

```text
All
Hide No Trade
LONG only
SHORT only
Entry Zone / Trigger Ready
Minimum EV
```

Scanner output includes:

- Symbol
- Signal
- Execution status
- EV Score
- Setup type
- Reason

---

### EV Score

EV Score is a ranking score for scanner results.

It combines:

- Setup score
- Entry Timing
- Risk Quality
- Signal stage
- Execution status
- No Trade penalty

Displayed as:

```text
EV: 0–100
```

---

### Backtest

Backtest helps evaluate the strategy on historical candles.

Backtest includes:

- Conservative TP/SL handling
- One-active-trade logic
- Cooldown
- Missed Entry
- Stale Plan
- Open trade tracking
- MFE
- MAE
- Profit Factor
- Fill Rate
- Total R
- Max Drawdown
- Expectancy
- Backtest Score /100

Backtest Score is a summary score based on:

```text
Total R
Winrate
Profit Factor
Drawdown
Fill Rate
Expectancy
MFE / MAE
Sample size
```

---

### Forward Test Log

Forward Log records live signals and tracks how they perform over time.

It stores:

- Symbol
- Timeframe
- Signal
- Playbook
- Stage
- Entry
- SL
- TP1
- TP2
- EV Score
- Risk Quality
- Status
- Outcome
- Result R
- MFE
- MAE
- After 5 candles
- After 10 candles
- After 20 candles

Forward Log also includes playbook statistics:

```text
Playbook
Number of outcomes
Winrate
Expectancy
```

CSV export is supported.

---

### Manual Position Mode

If you enter a trade manually, you can use Manual Position Mode.

Workflow:

```text
Click "Tôi đã vào lệnh"
→ Input real entry price
→ Confirm entry
→ Tool recalculates TP/SL from your actual entry
→ Tool stops waiting for entry/stale state
→ Tool switches to position management mode
```

This is useful when your real Binance entry is different from the planned entry.

---

### UI Modes

V3 Official includes multiple interface modes.

```text
Research Mode
Trade Mode
Debug Mode
Trade Focus
```

#### Research Mode

For full analysis:

- Chart
- Trade Plan
- Market Context
- Scanner
- Backtest
- Forward Log

#### Trade Mode

For live manual execution:

- Trade Plan
- Entry Zone
- Entry
- TP/SL
- Risk Quality
- No Trade Guard
- Manual Entry
- Copy Trade

#### Debug Mode

For testing and review:

- Backtest
- Forward Log
- Debug information

#### Trade Focus

A simplified mode for focusing only on the current trade plan.

---

## Recommended Workflow

```text
1. Open the tool
2. Scan Top 25
3. Filter by EV / Entry Zone / Trigger Ready
4. Analyze best setup
5. Check Playbook
6. Check No Trade Guard
7. Check Risk Quality
8. Check Net RR
9. Copy trade plan
10. Enter manually on Binance if valid
11. Use Manual Position Mode after entering
12. Track result in Forward Log
```

---

## Copy Trade Format

The Copy Trade button outputs a clean format:

```text
SYMBOL
SIGNAL
ENTRY ZONE: ... | ENTRY PRICE: ...
TP1: ... | TP2: ... | SL: ...
```

If the setup should not be traded, a warning is added:

```text
⚠ [reason]
SYMBOL
SIGNAL
ENTRY ZONE: ... | ENTRY PRICE: ...
TP1: ... | TP2: ... | SL: ...
```

---

## Tech Stack

- HTML
- Vanilla JavaScript
- Tailwind CDN
- Lightweight Charts
- Binance Futures public market data API
- GitHub Pages

---

## Deployment

This project is deployed with GitHub Pages.

Main file:

```text
index.html
```

GitHub Pages source:

```text
main branch / root
```

Live URL:

```text
https://dino6298.github.io/btc_analyzer/
```

---

## Repository Structure

Recommended structure:

```text
btc_analyzer/
│
├── index.html
├── README.md
├── CHANGELOG.md
├── LICENSE
├── .gitignore
├── .nojekyll
│
└── docs/
    └── screenshots/
        ├── dashboard.png
        ├── scanner.png
        └── backtest.png
```

---

## Version

```text
Version: V3 Official
Build: 2026-05-16
Execution: Manual only
```

---

## Changelog Summary

### V3 Official

Added:

- Playbook Engine
- Daily Risk Guard
- Trade / Research / Debug UI modes
- Trade Focus Mode
- Scanner Lite / Deep mode
- EV Score Scanner
- Scanner filters
- Backtest Score /100
- Forward Log statistics
- Forward Log CSV export
- Binance exchangeInfo validation
- Fee / slippage / Net RR
- Manual Position Mode
- Copy trade warning

Improved:

- Realtime execution safety
- Backtest logic
- Profit Factor calculation
- UI readability
- Chart autoscale
- No Trade Guard logic
- Binance price/quantity validation

Fixed:

- False TP/SL detection from live kline high/low
- Manual entry stale/wait conflict
- Scanner Top 25 performance
- Copy trade formatting
- CSV export syntax issue
- Forward Log syntax issue

---

## Limitations

This tool is not a fully automated trading bot.

Current limitations:

- It does not place orders automatically.
- It does not guarantee profitability.
- Backtest results may not represent future performance.
- Public market data may be delayed or unavailable.
- Fee, slippage and funding estimates are approximate.
- Futures trading involves high risk.

---

## Disclaimer

This project is for:

- Research
- Education
- Backtesting
- Forward testing
- Trading decision support

It is **not financial advice**.

Crypto futures trading is highly risky. Always manage risk carefully and never trade with money you cannot afford to lose.

You are responsible for your own trading decisions.

---

## Author

Built by Dino.

```text
Watermark: dino98
```
