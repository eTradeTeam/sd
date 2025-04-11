# Money Management

This document outlines how our team handles **capital allocation, position sizing, and risk controls** across all strategies. By applying standardized money management principles, we ensure each system adheres to defined **risk thresholds** and maintains consistency in how trades are sized and monitored.

---

## 1. Why Money Management Matters

1. **Control Drawdowns**  
   - Even a profitable strategy can cause severe account drawdowns if trades are oversized.  
   - Proper money management protects capital during losing streaks or unexpected market shocks.

2. **Stabilize Returns**  
   - Adapting position size to volatility, account equity, or other factors helps smooth the equity curve.  
   - Reduces the probability of catastrophic losses.

3. **Increase Strategy Longevity**  
   - Strategies often go through up/down cycles. Having a controlled risk approach ensures a **longer runway** to recover when performance dips.

---

## 2. Key Concepts

1. **Risk Per Trade**  
   - The **fixed amount** (or fraction of account) you’re willing to lose if a single trade goes wrong.  
   - Often expressed as a percentage of total equity (e.g., 1% risk per trade) or a fixed dollar amount.

2. **Drawdown Thresholds**  
   - Define maximum allowable drawdown (peak-to-valley) in your strategy or total portfolio.  
   - Some traders stop or reduce trading if drawdowns exceed, say, **25%** of total equity.

3. **Position Sizing**  
   - Determining how many shares, contracts, or lots to trade based on risk parameters (e.g., volatility-based, fixed fractional).  
   - Often **the most impactful factor** in controlling risk.

4. **Leverage**  
   - Using borrowed funds or margin can amplify gains/losses.  
   - Must be carefully managed to avoid margin calls or large drawdowns.

---

## 3. Position Sizing Methods

1. **Fixed Fractional**  
   - Risk a fixed percent of total equity on each trade (e.g., 1% risk).  
   - For example, if your account is \$100,000 and you risk 1% (\$1,000) per trade, and your stop is \$2 away, you’d buy 500 shares.  
   - Pros: Scales up (and down) with account size, limiting risk during losing streaks.

2. **Volatility-Based** (ATR, Standard Deviation)  
   - Adjust position size based on the market’s volatility, so you risk fewer shares/contracts in high-volatility conditions.  
   - For example, if the ATR is large, you reduce size to keep dollar risk constant.  
   - Pros: Helps maintain a consistent risk across varying market conditions.

3. **Fixed Dollar / Lots**  
   - Trade a **constant number of shares/lots** (e.g., always trade 1 contract or 100 shares).  
   - Simpler to implement, but doesn’t dynamically adjust to account size or volatility.  
   - Can be risky if account equity changes significantly.

4. **Pyramiding / Scaling**  
   - Enter a position incrementally (e.g., 50% initial, 25% if price moves favorably, final 25% after further confirmation).  
   - Must track aggregated risk carefully to avoid oversizing.

---

## 4. Stop-Loss & Risk Controls

1. **Stop-Loss Types**  
   - **Percentage-Based** (e.g., 2% below entry)  
   - **ATR-Based** (e.g., 2× ATR from entry)  
   - **Swing/Structure-Based** (below last swing low or major support)

2. **Trailing Stops**  
   - Lock in profits as the trade moves in your favor.  
   - For instance, a stop that trails behind price by 2× ATR.

3. **Daily/Weekly Loss Limits**  
   - Some traders cap how much they can lose in a single day or week.  
   - If it hits that cap, they stop trading until the next session or period.

4. **Capital Risk Limits**  
   - You might set a rule: “Never have more than 10% of the account at risk across all open positions.”  
   - This ensures multiple concurrent trades won’t blow the account if they all fail at once.

---

## 5. Implementation in the Strategy Framework

1. **Integration with Entry/Exit Logic**  
   - The moment a strategy decides to enter a trade, it calls a **position sizing function** (see [Strategy_Framework.md](./Strategy_Framework.md)).  
   - That function calculates the lot/shares to trade based on the stop distance and risk per trade.

2. **Dynamic Adjustments**  
   - If the strategy uses a **volatility-based approach**, it recalculates position size whenever volatility changes (e.g., each new bar, or daily).  
   - Must ensure the platform can handle mid-position sizing changes if you scale in or out.

3. **Code Snippets**  
   - Example (pseudo-code for fixed fractional):
     ```
     riskPerTrade = accountEquity * 0.01
     stopDistance = entryPrice - stopPrice
     positionSize = riskPerTrade / stopDistance
     ```
   - Then round to the nearest valid lot size.

---

## 6. Portfolio Perspective

1. **Multiple Strategies**  
   - If you run multiple strategies at once, track **aggregate risk**.  
   - One approach is to reduce position size if your total open risk from other trades is already high.

2. **Correlation**  
   - Strategies that are highly correlated (e.g., multiple equity trend systems) can increase drawdowns if they all fail at once.  
   - Consider limiting how many correlated trades can be open simultaneously.

3. **Capital Allocation**  
   - Some traders allocate a fixed fraction of their account to each strategy (e.g., 20% to a mean reversion system, 30% to a trend-following system, etc.).  
   - Periodically rebalance if one strategy grows faster or slower than others.

---

## 7. Monitoring & Reassessment

1. **Track Real-Time Risk**  
   - Ensure your trading platform or a custom tool keeps a live tab on total margin usage, potential drawdown, and open risk.

2. **Review Periodically**  
   - Conduct monthly or quarterly reviews of your money management rules.  
   - If your risk tolerance changes or you see repeated large drawdowns, adjust the approach.

3. **Account Growth Adjustments**  
   - As the account grows/shrinks, your risk in dollar terms should scale accordingly if you use a **fixed fractional** method.  
   - Be cautious about ramping up risk too quickly if you have a lucky winning streak.

---

## 8. Best Practices

1. **Set Realistic Risk Limits**  
   - Many professionals cap risk per trade at **0.5%–2%** of total equity.  
   - 2% risk might be acceptable for a more volatile approach, 0.5% is more conservative.

2. **Test Your Money Management Rules**  
   - Run backtests that include the actual position sizing rules.  
   - Overly optimistic backtests might ignore real transaction costs, slippage, or partial fills.

3. **Stay Consistent**  
   - Resist the urge to arbitrarily deviate from your rules (e.g., “doubling up” after a big loss).  
   - Emotional decisions often lead to bigger drawdowns.

4. **Document Everything**  
   - Keep track of your chosen method (fixed fractional, ATR-based, etc.) in your strategy notes.  
   - Log any changes you make to your money management parameters.

---

## 9. Next Steps

1. **Incorporate into Strategy Codes**  
   - Ensure each new or existing strategy references your money management modules consistently.  
2. **Review in Rigorous Testing**  
   - When you do [walk-forward](./rigorous_test.md) or [incubation](./incubation.md), confirm that money management is part of the testing environment.  
3. **Refine Over Time**  
   - If you see repeated large drawdowns or low usage of available capital, fine-tune your approach accordingly.

---

**Conclusion**: Money management is the **cornerstone** of long-term trading success. By defining clear risk rules, position sizing methods, and portfolio-level constraints, we protect our capital while enabling steady growth through profitable strategies.