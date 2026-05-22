# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<!-- markdownlint-disable MD024 -->

## [0.2.0] - 2026-05-22

### Added

- `Weekly_ATR_Fib_Bias_Levels.pine` — Weekly ATR-derived Fibonacci bias levels overlay, providing dynamic support/resistance zones scaled to the current week's true range.
- `VWAP_Pro_Institutional_Suite.pine` — Pine v6 institutional-grade VWAP indicator with multi-anchor VWAP, three-level deviation bands, market state engine (trend/range classification), signal system (continuation, mean reversion, reclaim, bounce), institutional filters (relative volume, volatility, chop, VWAP/TWAP lead), session overlays (London, New York), and on-chart performance dashboard.
- `researchers/` — 7 SSRN academic papers on market microstructure, liquidity, and quantitative trading strategy; referenced as the theoretical foundation for indicator design decisions.
- `docs/` — Project documentation: style guide, repository overview, getting-started guide, FAQ, and versioning/compatibility notes.
- `examples/` — Reusable scaffolding including three script templates (indicator, strategy, library), plotting/alert/utility/risk-management snippets, and four step-by-step tutorials covering basic walkthrough, strategy conversion, no-repaint techniques, and backtesting best practices.
- `indicators/` — 12 reference indicators spanning beginner to advanced: MA crossover, RSI basic, RSI divergence detector, volatility bands, session high/low, support/resistance zones, market structure tool, liquidity sweep detector, Smart Money Concepts (order blocks + FVG), multi-timeframe trend analyzer, MTF trend dashboard, and volume profile lite.
- `strategies/` — 4 fully backtestable strategies with entry/exit logic and risk management: MA crossover, RSI mean reversion, session breakout, and liquidity sweep reversal.

## [0.1.0] - 2026-05-22

### Added

- `ICT_SMC_Strategy.pine` — Pine Script v6 strategy implementing the full ICT / Smart Money Concepts pipeline: liquidity sweep → MSS → displacement → FVG → OTE retracement → OB / Breaker confluence → entry → opposite-side liquidity target.
- Liquidity-pool tracking for Equal Highs/Lows, PDH/PDL, Asian H/L, Weekly H/L, each independently togglable.
- Multi-bar tolerant liquidity sweep detection with a configurable confirmation window (0–10 bars; 0 = strict same-bar sweep).
- Market structure module: BOS, MSS, and CHoCH detection from confirmed pivots, with MSS firing whenever a sweep precedes the structural break (independent of established trend direction).
- Displacement filter using ATR-multiplied body size combined with a close-near-extreme constraint.
- Fair Value Gap detection with three entry modes (First Touch, Midpoint, Full Mitigation) and per-zone mitigation tracking.
- Order Blocks with Wick or Body boundary modes, and Breaker Blocks created when an OB fails at an MSS.
- Optimal Trade Entry zone (0.618 / 0.705 / 0.79 Fibonacci retracement) gated by a Premium/Discount equilibrium filter.
- Killzone session filters for London, New York, and PM Reversal windows, each with configurable times and timezones.
- Higher-timeframe bias filter using HTF pivots with `lookahead_off`, non-repainting.
- Risk management: three take-profit modes (Fixed RR / Liquidity Target / Opposing FVG), four Risk % presets (0.25 / 0.5 / 1 / 2), five RR ratios (1:1 through 1:5), and a configurable SL tick buffer.
- Strategy-compatible alerts via `alert()` for bullish/bearish MSS, liquidity sweeps, long/short entries, and position close.
- On-chart dashboard reporting win rate, profit factor, average RR, total trades, long/short split, average hold time, HTF bias, current session, and market state.
- Recommended input presets documented in-file for XAUUSD, EURUSD, GBPUSD, NAS100, and US30.
