## **Table of Contents:**

- [**Strategy Development Main**](../README.md)
  - [Strategy_Factory Process](./strategy_factory.md)
  - [**Our Process**](./README.md)
    - [Idea Generation & Signal Identification](./identify_signals.md)
    - [Combine Signals Into Strategies](./strategies.md)
    - [Initial Feasibility Testing](./feasibility_testing.md)
    - [Rigorous Testing & Validation](./rigorous_test.md)
    - [Incubation](./incubation.md)
    - [Strategy Framework Integration](./Strategy_Framework.md)
    - [Money Management](./Money_Management.md)
    - [Portfolio Management](./Portfolio_Management.md)
    - [Strategy_Categories](./strategy_types.md)

---

# Incubation

After a strategy has undergone **feasibility testing** and **rigorous validation** (walk-forward, Monte Carlo, etc.), the next step is **incubation**—a live observation phase without committing real capital. Incubation helps ensure that the strategy’s performance in real market conditions **aligns with** its backtested behavior.

---

## 1. Purpose of Incubation

1. **Real-Time Validation**  
   - Verify that signals and orders trigger as expected in a real-time data environment.  
   - Identify any discrepancies between backtested fills and actual or simulated intraday price movements.

2. **Emotional Discipline Check**  
   - Incubation tests if you can follow the strategy’s signals without second-guessing or interfering.  
   - Helps build confidence in the system before risking money.

3. **Identify Hidden Weaknesses**  
   - Some issues (e.g., slippage, data feed quirks, real-time order flow) might not be apparent in historical tests.  
   - The strategy may respond differently to changing volatility or newly emerging market conditions.

---

## 2. Incubation Methods

1. **Paper Trading / Simulated Accounts**  
   - Many brokerage platforms (e.g., TradeStation, NinjaTrader, MultiCharts) offer **demo accounts** that replicate real-time market data.  
   - The strategy’s trades are executed virtually, tracking P/L and drawdowns.

2. **Forward Watching / “Phantom” Trading**  
   - If a platform doesn’t support demo trading, you can log each trade signal manually (spreadsheet or dedicated app).  
   - Compare these signals at day’s end to what the actual market movement was.

3. **Minimal Live Capital (Optional)**  
   - Some traders prefer to test strategies live with **1 micro contract** or a very small position size.  
   - This approach exposes you to real commission/slippage but keeps financial risk minimal.

---

## 3. Incubation Duration & Criteria

1. **Time Period**  
   - Many adopt Kevin Davey’s recommendation of **3–6 months** (sometimes up to 9 months) for forward observation.  
   - The goal is to cover **multiple market conditions** (trending, volatile, choppy).

2. **Performance Thresholds**  
   - Decide on acceptable drawdown and return relative to backtested expectations.  
   - If the system deviates significantly (e.g., 2× historical max drawdown), you might **stop and review**.

3. **Trade Count**  
   - Ensure you collect a **meaningful number of trades** (e.g., at least 20–30) to draw conclusions about real-time performance.

---

## 4. Monitoring & Data Collection

1. **Live Equity Curve**  
   - Chart the strategy’s equity or net P/L day by day (or trade by trade).  
   - Compare the new equity path to the historical backtest’s shape/range.

2. **Discrepancy Analysis**  
   - Track slippage vs. expected fills.  
   - Record missed trades or partial fills in fast markets.  
   - If using a partial or micro contract approach, note any differences from full-size risk/position sizing.

3. **Routine Logs**  
   - Keep a “strategy journal” documenting daily signals, trades taken, errors encountered.  
   - If you see repeated issues (e.g., erroneous signals at market open), investigate.

---

## 5. Handling Drawdowns & Adapting

1. **Stop-Trading Rules**  
   - Predefine a **stop-trading threshold**—for example, if your drawdown exceeds 1.5× the historical max, pause the system and reassess.  
   - Strictly adhere to these thresholds to prevent emotional or impulsive decisions.

2. **System Tweaks**  
   - Ideally, **avoid major tweaks** during the incubation period so you can get a valid read on the system’s unmodified logic.  
   - If catastrophic performance or coding errors appear, do a **post-mortem** and fix them, then restart incubation.

3. **Communication with the Team**  
   - If you spot systematic issues, open a GitHub issue or discuss in your Discord/Zoom channels.  
   - Get feedback from testers or developers who might have insights on improvements.

---

## 6. Transition from Incubation to Live Trading

1. **Meeting Performance Benchmarks**  
   - Once the strategy meets or **closely approximates** backtest expectations (in terms of win rate, average trade, drawdowns, etc.), it’s a strong candidate for real-money deployment.

2. **Scaling In**  
   - Many prefer to **start small** (1 contract, minimal share size) in a live account before committing full capital.  
   - Increase size gradually if performance stays in line with historical metrics.

3. **Ongoing Monitoring**  
   - Even after “going live,” track real trades daily or weekly.  
   - Conduct periodic reviews (monthly or quarterly) to detect any degradation in performance.

---

## 7. Common Pitfalls

- **Tweak-Itis**: Constantly adjusting parameters whenever losses occur undermines a true incubation test.  
- **Short Incubation**: Rushing to live trade with only a few days/weeks of forward data can backfire.  
- **Ignoring Real-World Constraints**: Overlooking commissions, slippage, overnight margin requirements, or broker-specific nuances can produce misleading results.

---

## 8. Summary & Next Steps

1. **Proven Strategy**  
   - If the strategy performs well throughout incubation, you have a **better chance** of real-world success.  
2. **Deployment**  
   - Move forward with careful position sizing (see [Money_Management.md](./Money_Management.md)).  
3. **Continuous Evaluation**  
   - Keep tracking the system’s live performance and refer back to your historical benchmarks for ongoing comparison.

---

**Conclusion**: Incubation is a **crucial final checkpoint** in our strategy factory. By paper trading or using minimal capital in real-time, you verify a strategy’s actual performance and build confidence before risking larger sums.