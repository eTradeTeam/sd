# Strategies

This document explains how we **combine signals** into cohesive, testable trading strategies. While each signal can provide an edge in isolation, a well-structured strategy integrates multiple components (entries, exits, filters, money management) to **maximize robustness** and adapt to varying market conditions.

---

## 1. What Is a Strategy?

A **strategy** is a **rule-based system** that governs:
1. **Entry Logic**: When and how you enter a position (long or short).  
2. **Exit Logic**: How you protect profits or limit losses (stop-loss, trailing stop, profit targets).  
3. **Filters & Conditions**: Additional rules that refine signals (e.g., avoid trading during certain times or if volatility is too high/low).  
4. **Risk Management**: How you size positions or cap drawdowns (see [Money_Management.md](./Money_Management.md)).

A strategy typically maps to a **specific category** (Trend Following, Mean Reversion, Momentum, etc.) but may blend features from multiple categories.

---

## 2. Combining Signals

1. **Primary Signals**  
   - These generate the **main trade triggers** (e.g., RSI(2) oversold reading for a mean reversion strategy).  
   - Decide if your strategy will have **one primary signal** or multiple (e.g., RSI + Bollinger Band combination).

2. **Filters & Confirmations**  
   - Additional rules that refine entries or exits. For instance:  
     - **Trend Filter**: Only take RSI-based mean reversion signals if the 200-day moving average is sloping up.  
     - **Time Filter**: Avoid trades during a major news announcement window.  
   - Filters can reduce noise but also reduce trading frequency.

3. **Exit Strategies**  
   - **Stop-Loss**: Hard or trailing stops to limit potential losses.  
   - **Profit Targets**: Partial or full exit at predefined profit levels.  
   - **Time-Based Exits**: Close positions after a certain number of bars/days if the trade hasn’t hit a target or stop.

4. **Indicator Convergence**  
   - Some strategies wait for **two or more signals** to align (e.g., MACD cross + price closing above the 20-day moving average).

5. **Market Environment Rules**  
   - Incorporate volatility or regime checks (e.g., trade only in high-vol environments).  
   - Distinguish between bullish/bearish market phases if relevant.

---

## 3. Examples by Category

1. **Trend Following**  
   - **Entry**: Moving average crossover.  
   - **Filter**: Must confirm with higher timeframe trend or ADX>25 indicating a trending environment.  
   - **Exit**: ATR-based trailing stop.

2. **Mean Reversion**  
   - **Entry**: RSI drops below 30, then crosses back above 30.  
   - **Filter**: Only valid if the price is within Bollinger Bands.  
   - **Exit**: Either exit at RSI>50 or after X bars.

3. **Momentum**  
   - **Entry**: Price makes new N-day high with above-average volume.  
   - **Filter**: Market sentiment or stock rank in top 20% by relative strength.  
   - **Exit**: Use a trailing stop or a fixed target (2× the initial risk).

4. **Breakout**  
   - **Entry**: Price closes above the prior day’s high (intraday or daily).  
   - **Filter**: Ensure the breakout bar has higher volume than average.  
   - **Exit**: Use a trailing stop or reversion signal (e.g., closes back below the breakout level).

---

## 4. Coding & Integration

1. **Strategy Framework**  
   - All strategies should integrate with our shared [Strategy_Framework.md](./Strategy_Framework.md) for consistency.  
   - This ensures entries, exits, and money management rules are **modular** and maintainable.

2. **Platform-Specific Implementation**  
   - **TradeStation EasyLanguage**: Typically one `.eld` or `.els` file per strategy.  
   - **NinjaTrader (C#)**: A separate strategy `.cs` file with OnBarUpdate, OnStateChange, etc.  
   - **MultiCharts (PowerLanguage)**: Similar structure to EasyLanguage code.

3. **Documentation**  
   - Keep a brief description of the strategy’s logic (entry/exit, filters, risk rules) in a companion `.md` file or code comments.  
   - If you add a new strategy, update the relevant library or tracking sheet.

---

## 5. Early Testing

1. **Feasibility Testing**  
   - When you first combine signals, run a quick test on a limited dataset to see if the approach yields any promise.  
   - Refer to [feasibility_testing.md](./feasibility_testing.md) for steps.

2. **Refining Rules**  
   - If performance is poor, consider adjusting filters or exit conditions.  
   - Avoid adding too many rules at once—**keep it simple** so you can isolate what helps or hurts performance.

---

## 6. Transition to Rigorous Testing

1. **Multi-Market & Parameter Testing**  
   - If the strategy looks promising, move to [rigorous_test.md](./rigorous_test.md).  
   - Test across **various instruments and timeframes** to ensure it’s not overfitted to a single dataset.

2. **Walk-Forward & Monte Carlo**  
   - Evaluate how the strategy performs in **out-of-sample** periods.  
   - Assess worst-case drawdowns via Monte Carlo.

3. **Incubation**  
   - If the strategy passes advanced testing, run it in a **paper-trading** or watch mode for ~3–6 months. See [incubation.md](./incubation.md).

---

## 7. Recommended Best Practices

1. **Simplicity First**  
   - Overly complicated strategies often fail in live markets due to overfitting.  
   - Start with a basic signal + filter structure, then **add complexity slowly** if needed.

2. **Check Correlation**  
   - If you plan to run multiple strategies simultaneously, measure **correlation** to avoid piling on the same risk.

3. **Regular Maintenance**  
   - Markets change; keep an eye on each strategy’s performance.  
   - Revisit your code, logic, and assumptions at regular intervals (monthly or quarterly).

---

## 8. Next Steps

1. **Money Management**  
   - After you define your strategy’s core logic, decide on position sizing, risk per trade, and drawdown rules. See [Money_Management.md](./Money_Management.md).

2. **Team Collaboration**  
   - Submit new or updated strategies via GitHub pull requests for peer review.  
   - Make sure to note which signals you’ve combined and why.

3. **Live Implementation**  
   - Once a strategy passes incubation, deploy it with caution—often starting with a minimal contract/shares to validate real-world fills and slippage.

---

**Conclusion**: Crafting a solid strategy means thoughtfully **combining** well-tested signals, exit rules, and risk controls into a coherent package. Keep your **documentation** clear, test thoroughly, and iterate based on evidence. By following this process, we ensure every new strategy meets our team’s standards for quality, reliability, and potential profitability.