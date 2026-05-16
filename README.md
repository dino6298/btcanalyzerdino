# Dino Futures Tool V3 Official

A lightweight HTML-only crypto futures decision-support dashboard for market analysis, opportunity scanning, backtesting, forward testing and risk management.

> Built for manual trading decision support. This tool does not place orders automatically.

## Live Demo

https://dino6298.github.io/btc_analyzer/

## Overview

Dino Futures Tool V3 Official helps analyze crypto futures setups using multiple layers of confirmation:

- Trade Playbook Engine
- Market Regime Filter
- Entry Zone / Entry Timing
- No Trade Guard
- Risk Quality Score
- EV Score Scanner
- Backtest Score /100
- Forward Test Log
- Manual Position Mode
- Binance Futures rule validation

The goal is not to generate random signals, but to filter out low-quality trades and support disciplined manual execution.

## Key Features

### Trade Plan Engine

- LONG / SHORT setup detection
- Entry Zone instead of a single fixed price
- TP1 / TP2 / SL generation
- Signal stage tracking:
  - SETUP_FORMING
  - WAIT_PULLBACK
  - ENTRY_ZONE
  - TRIGGER_READY
  - STALE_PLAN
  - MANUAL_ACTIVE

### Playbook Engine

Supported playbooks:

- FVG Continuation
- Trend Pullback
- Liquidity Sweep Reversal
- Breakout Retest
- Range Mean Reversion
- General Momentum

### Risk System

- No Trade Guard
- Risk Quality Score
- Safe / Balanced / Aggressive risk mode
- Fee and slippage adjustment
- Net RR calculation
- Daily Risk Guard
- Binance min order / tick size / step size validation

### Scanner

- Top 10 / Top 20 / Top 25 symbol scanner
- Lite Scan / Deep Scan mode
- EV Score ranking
- Filters:
  - Hide No Trade
  - LONG only
  - SHORT only
  - Entry Zone / Trigger Ready
  - Minimum EV

### Backtest

- Conservative TP/SL handling
- One-active-trade logic
- Cooldown
- Missed / Stale / Open tracking
- MFE / MAE
- Profit Factor
- Backtest Score /100

### Forward Testing

- Forward Log
- Outcome / resultR tracking
- MFE / MAE tracking
- Playbook statistics
- CSV export

### Manual Position Mode

After entering a trade manually, you can input your real entry price. The tool will then:

- Recalculate TP/SL from your actual entry
- Stop waiting for entry confirmation
- Switch into position management mode

## How to Use

1. Open the live demo.
2. Choose a symbol and timeframe.
3. Click **Analyze**.
4. Check:
   - Playbook
   - Entry Zone
   - Entry Price
   - TP1 / TP2 / SL
   - Risk Quality
   - No Trade Guard
   - Net RR
5. Use **Copy Plan** if the setup is valid.
6. If you enter manually, use **Manual Position Mode**.
7. Use Scanner and Forward Log to evaluate performance over time.

## Recommended Workflow

```text
Scan Top 25
→ Filter EV / Entry Zone / Trigger Ready
→ Analyze best setup
→ Check No Trade Guard
→ Check Net RR
→ Copy plan
→ Forward test result
