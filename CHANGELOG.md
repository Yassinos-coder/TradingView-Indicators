# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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
