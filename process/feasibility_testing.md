# Feasibility Testing

This document outlines how we **quickly assess** whether a new strategy idea or signal combination has potential before investing time in rigorous testing and development. The goal is to **screen out weak ideas early**, so we can focus on those that show at least a preliminary edge.

---

## 1. Purpose of Feasibility Testing

1. **Save Time & Resources**  
   - Avoid lengthy parameter optimization, in-depth walk-forward testing, or Monte Carlo analysis on strategies that clearly lack any performance edge.

2. **Early Validation**  
   - Quickly see if an idea demonstrates a **positive expectancy** (i.e., average profit per trade is above zero, with manageable drawdowns) over a short test period.

3. **Low-Fidelity Check**  
   - Feasibility tests are not final proofs of robustness. Instead, they act as **gatekeepers** to decide whether a strategy is worth deeper exploration.

---

## 2. Data & Timeframe

1. **Limited Lookback**  
   - We often pick **1–2 years** of historical data or a specific, relevant market regime (e.g., a trending year vs. a volatile year).  
   - This reduces computation time and helps us identify glaring issues quickly.

2. **Representative Market Conditions**  
   - Ensure your small sample includes different market phases (e.g., a bullish trend, a sideways phase) if possible.  
   - This can highlight a strategy’s major vulnerabilities right away.

3. **Single Instrument or Small Basket**  
   - Typically, test on **one or two** instruments (e.g., ES futures, SPY ETF, or a major Forex pair) that are **highly liquid** and reflect a broad market environment.

---

## 3. Testing Process

1. **Code the Strategy**  
   - Implement the strategy logic in your platform (TradeStation, NinjaTrader, etc.) with minimal complexity (few parameters).

2. **Run a Quick Backtest**  
   - Use your chosen short data window.  
   - Keep all settings consistent (e.g., 1-minute bars, daily bars, or whichever timeframe suits your idea).

3. **Check Key Metrics**  
   - **Net Profit or Profit Factor**: Are we netting a profit over the test period?  
   - **Drawdown**: Is the strategy’s worst drawdown so large that it’s not practical?  
   - **Trade Count**: Does the system produce enough trades to be statistically meaningful?

4. **Simple Optimization (Optional)**  
   - If you have **one or two** parameters (e.g., a moving average length), do a quick sweep (e.g., 10–100 in steps of 10) to see if there’s a stable zone with net positive returns.  
   - Avoid complex multi-parameter optimizations at this stage—this is a **low-fidelity** check only.

---

## 4. Go/No-Go Criteria

While each team has its own thresholds, here are some common guidelines:

1. **Basic Profitability**  
   - **Net profit > 0** over the test period.  
   - Profit factor > 1.1 or 1.2, indicating the system makes more on winning trades than it loses on losing trades.

2. **Acceptable Drawdown**  
   - Max drawdown is not excessive relative to net profit (e.g., return/drawdown ratio of at least 1.0 or higher).  
   - The system doesn’t exhibit single-trade meltdowns or extended consecutive losing streaks that are unrealistic to stomach.

3. **Reasonable Number of Trades**  
   - At least 20–30 trades in the limited sample, so the results aren’t entirely luck-driven.  
   - If the system triggers **extremely few** trades, it may need rethinking or a bigger data window.

4. **Parameter Stability**  
   - If you do a small parameter sweep, look for a **broad plateau** of decent performance rather than one extremely narrow peak.  
   - A strategy that only works at a single, highly specific parameter setting often doesn’t hold up later.

---

## 5. Outcomes

1. **Promising → Move On**  
   - If the strategy shows **positive results** and meets your basic criteria, proceed to [rigorous_test.md](./rigorous_test.md).  
   - Further testing will confirm whether these early gains are real or happenstance.

2. **Weak or Negative → Reject / Refine**  
   - Strategies that fail feasibility testing can either be **discarded** or significantly refined before retesting.  
   - Look for obvious flaws in logic or signals; sometimes a small tweak can revive an idea.

3. **Uncertain → Expand Test**  
   - If results are borderline (slightly profitable, but high drawdown), consider testing on a slightly larger data window or an additional instrument.  
   - Decide whether to adjust the strategy logic or gather more evidence.

---

## 6. Best Practices & Tips

- **Keep It Simple**: Don’t add advanced filters or complicated money management rules yet. This stage is purely about **core logic**.  
- **Document Everything**: Record in a `.md` file or spreadsheet the **date**, **instrument**, **timeframe**, **key performance stats**, and any notes.  
- **Align with Kevin Davey’s Factory Approach**: Remember that Davey recommends tossing out the majority of ideas that fail simple initial checks—**only the strongest** proceed to advanced testing.  
- **Beware Overfitting**: Resist the temptation to do heavy optimization here. Overfitting can mask reality and inflate your early hopes.

---

## 7. Next Steps

1. **Rigorous Testing**  
   - If your system passes feasibility, see [rigorous_test.md](./rigorous_test.md) for multi-market evaluations, walk-forward testing, and Monte Carlo analysis.

2. **Strategy Refinement**  
   - Integrate more robust exit logic, incorporate basic risk management, or tweak parameters carefully if you believe the concept is solid.

3. **Team Collaboration**  
   - Share your feasibility results via GitHub issues, Discord, or direct pull requests.  
   - Gather feedback from team members to decide on final steps.

---

**Conclusion**: Feasibility testing is the “quick filter” that keeps us from sinking valuable time into ideas without real market viability. By following this process—and documenting results systematically—we ensure that only the **most promising strategies** advance to more resource-intensive phases.