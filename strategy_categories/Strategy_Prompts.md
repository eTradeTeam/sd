# Strategy Development Prompts

## How to act
Absolutely! Here’s a **master prompt** to frame our collaboration. Copy/paste this into your next message, and I’ll adopt the role of a systematic, profit-driven quant developer:

---

### **Role & Objective**  
*"Act as a world-class quantitative algorithmic trading strategist. Your goal is to design, test, and deploy highly profitable algorithmic strategies using rigorous statistical methods. Prioritize strategies with asymmetric risk/reward profiles, robustness across market regimes, and minimal correlation to existing portfolios. Assume access to high-quality historical data (tick, OHLC, volume) and low-latency execution infrastructure. Focus on actionable, institution-grade logic—no theoretical fluff."*

---

### **Step-by-Step Approach**  
#### 1. **Categorize Strategies**  

##### **Prompt 1**:  
    *"Based on historical market data and academic literature, list all major trading strategy categories (e.g., Trend Following, Mean Reversion, Momentum, Breakout, Statistical Arbitrage, Volatility Targeting, Machine Learning-Driven, Market Sentiment). For each category, provide:  
    - A definition.
    - Typical market conditions where it thrives (e.g., high volatility, ranging markets).  
    - Core principles (e.g., ‘buy high, sell higher’ for momentum)."
    - Core hypothesis (e.g., "Trends persist due to behavioral biases").   
    - Ideal market conditions (e.g., low volatility for mean reversion). 
    - applicable securities such as Stocks, ETFs, Futures, Options, etc."*

    **Purpose**: Establish a foundation of strategy types and their contexts.




##### **Prompt 2**  
    *"Act as a quantitative strategist. For the [strategy category] category, provide a detailed breakdown:  
    1. **Core Hypothesis**: Explain the market inefficiency or behavioral bias the category exploits.  
    2. **Top 3 Indicators**:  
    - List indicators historically linked to profitability in this category.  
    - For each, explain why it works (e.g., ‘Bollinger Bands identify overextended prices’).  
    1. **Example Strategies**:  
    - Provide 2-3 unique strategy variations per indicator.  
    - Include logic, optimal parameters, and pseudocode snippets.  
    1. **Market Conditions**: Describe when the category thrives (e.g., high volatility, low volume).  
    2. **Trading Styles**: Map strategies to scalping, intraday, swing, or position trading.  
    3. **Timeframe Suitability**: Specify ideal timeframes (e.g., 1hr for swing) and why.  
    4. **Key Risks**: Highlight vulnerabilities (e.g., whipsaws in ranging markets).  
    5. **Risk Management Tactics**: Suggest stop-loss, position sizing, or hedging rules.  

    Format the output with clear headers and bullet points."*

#### 2. **Indicator-Strategy Mapping**  
   - Assign indicators to categories (e.g., Bollinger Bands → Mean Reversion; ADL → Breakout).  
   - Rank indicators by historical efficacy (e.g., "RSI has 55% win rate in ranging markets").  

    **Prompt**:  
    *"For each strategy category (trend following, mean reversion, etc.), list the top 5 technical or statistical indicators historically associated with profitable strategies. Include:  
    - The indicator’s formula/logic.  
    - Why it works for the category (e.g., Bollinger Bands for mean reversion due to reversion to the mean).  
    - Timeframe suitability (e.g., RSI on 1hr for swing trading)."*

    **Purpose**: Connect indicators to strategy types and filter by practicality.

#### 3. **Generate Unique Strategies**  
   - For each indicator-category pair, create 3 variations:  
     - **Baseline**: Classic implementation (e.g., MACD crossover).  
     - **Enhanced**: Add filters (e.g., MACD + volume surge).  
     - **Hybrid**: Combine with uncorrelated indicators (e.g., MACD + Hurst Exponent).  

    **Prompt**:  
    *"For the [indicator] in the [strategy category] category, design 3 unique strategy variations. For each:  
    - Describe the logical trigger (e.g., ‘Buy when RSI < 30 and price crosses above 20-day SMA’).  
    - Specify optimal parameters (e.g., RSI period = 14, SMA period = 20).  
    - Add pseudocode for clarity.  
    - Highlight what makes it distinct from other variations (e.g., combining volume filters)."*

    **Example**:  
    *"For Bollinger Bands in the mean reversion category, create:  
    1. Classic Bollinger Reversion (price reverts to middle band).  
    2. Squeeze Breakout + Reversion Hybrid.  
    3. Volatility-Weighted Z-Score Reversion."*

    **Purpose**: Avoid redundancy and ensure strategies are novel and actionable.

#### 4. **Optimize for Trading Style**  
   - Map strategies to: Scalping (1min-5min), Intraday (15min-1hr), Swing (4hr-daily), Position (weekly+).  
   - Adjust parameters (e.g., shorter MA periods for scalping).  

    **A: Assign Strategies to Trading Styles**  

    **Prompt**:  
    *"Classify the following strategies into trading styles (scalping, intraday, swing, position trading):  
    - [Strategy 1]: Relies on 1-minute candles and 2-point profit targets.  
    - [Strategy 2]: Uses daily closing prices and holds for 1–3 weeks.  
    For each style, explain:  
    - Ideal timeframes (e.g., 1min for scalping).  
    - Required liquidity/volatility.  
    - Risk management adjustments (e.g., tighter stops for scalping)."*

    **Purpose**: Match strategies to practical execution constraints.

    **B: Optimize Timeframes and Parameters**

    **Prompt**:  
    *"Classify the following strategies into trading styles (scalping, intraday, swing, position trading):  
    - [Strategy 1]: Relies on 1-minute candles and 2-point profit targets.  
    - [Strategy 2]: Uses daily closing prices and holds for 1–3 weeks.  
    For each style, explain:  
    - Ideal timeframes (e.g., 1min for scalping).  
    - Required liquidity/volatility.  
    - Risk management adjustments (e.g., tighter stops for scalping)."*

    **Purpose**: Match strategies to practical execution constraints.

#### 5. **Backtest & Validate**  
   - Demand:  
     - Walk-forward analysis (rolling out-of-sample testing).  
     - Sharpe > 1.5, Max Drawdown < 15%, Profit Factor > 2.  
   - Stress-test across: Black Swan events, regime shifts (e.g., 2020 COVID crash).  

    **Prompt**:  
    *"Design a backtesting protocol for [strategy name] to evaluate:  
    - Performance across 3 market regimes (trending, ranging, volatile).  
    - Sensitivity to parameter changes (e.g., walk-forward analysis).  
    - Overfitting risks and how to mitigate them (e.g., out-of-sample testing).  
    Provide hypothetical Sharpe ratio, max drawdown, and win rate ranges for realism."*

    **Purpose**: Stress-test strategies before deployment.

#### 6. **Build Diversified Portfolio**  
   - Combine strategies with correlation < 0.3.  
   - Allocate capital using volatility scaling (e.g., risk parity).  

    **Prompt**:  
    *"Create a portfolio of 3 non-correlated strategies (e.g., trend + mean reversion + breakout). For each:  
    - Explain how they complement each other.  
    - Allocate capital based on volatility scaling.  
    - Add rules for dynamic weight adjustment (e.g., reduce leverage during low volatility)."*

    **Purpose**: Diversify risk and enhance consistency.

#### 7. **Code Implementation**  
   - Provide production-ready Python/pineScript snippets with:  
     - Real-time data handling.  
     - Slippage/latency simulation.  
     - API integration (e.g., Alpaca, Binance, MT5).  

    **Prompt**:  
    *"Convert the [strategy name] pseudocode into Python code with:  
    - Modular functions for signal generation, backtesting, and visualization.  
    - Integration with Oanda’s API for live trading.  
    - Comments explaining key steps (e.g., ‘Calculate rolling Z-score here’)."*

    **Example Output**:  
    ```python  
    def calculate_zscore(series, window):  
        return (series - series.rolling(window).mean()) / series.rolling(window).std()  
    ```

    **Purpose**: Bridge theory to execution.
---

### **Example Output Format**  
### Strategy: ADL Mean Reversion + Volatility Surge (Swing Trading)  
- **Category**: Mean Reversion + Breakout Hybrid  
- **Indicator**: Accumulation Distribution Line (ADL) + ATR  
- **Logic**: Short when ADL Z-score > 2 **and** ATR > 20-day average (volatility confirms extreme distribution).  
- **Timeframe**: 4hr (optimal balance between noise and signal).  
- **Pseudocode**:  
  ```python  
  if (adl_zscore > 2) and (ATR(20) > SMA(ATR(20), 50)):  
      enter_short(stop_loss=resistance + 2*ATR, take_profit=support - 2*ATR)  
  ```  
- **Edge**: Combines statistical extremes with volatility expansion, reducing false reversions.  


---

### **Trigger This Workflow**  
Paste this prompt at the start of your next message:  
*"Act as a world-class quant developer. Let’s begin with Step 1 (Categorize Strategies). For each category, provide:  
1. Core hypothesis.  
2. Best-performing indicators (ranked).  
3. Example strategy with edge.  
Proceed step-by-step and ask clarifying questions as needed."*  

I’ll respond with the precision of a hedge fund quant—no filler, just actionable alpha.


### **Final Workflow Summary**  
1. **Categorize** strategies.  
2. **Link indicators** to categories.  
3. **Generate unique strategies** per indicator.  
4A. **Assign** to trading styles/timeframes.  
4B. **Optimize** parameters.  
5. **Backtest** rigorously.  
6. **Combine** into portfolios.  
7. **Code** for execution.  


----

---------

------



Here’s a **detailed prompt** to systematically expand each strategy category, including core principles, edge, indicators, timeframes, and trading styles:  

---

### **User Prompt**  
*"Act as a quantitative strategist. For the [strategy category] category (e.g., trend following, mean reversion), provide a detailed breakdown:  
1. **Core Hypothesis**: Explain the market inefficiency or behavioral bias the category exploits.  
2. **Top 3 Indicators**:  
   - List indicators historically linked to profitability in this category.  
   - For each, explain why it works (e.g., ‘Bollinger Bands identify overextended prices’).  
3. **Example Strategies**:  
   - Provide 2-3 unique strategy variations per indicator.  
   - Include logic, optimal parameters, and pseudocode snippets.  
4. **Market Conditions**: Describe when the category thrives (e.g., high volatility, low volume).  
5. **Trading Styles**: Map strategies to scalping, intraday, swing, or position trading.  
6. **Timeframe Suitability**: Specify ideal timeframes (e.g., 1hr for swing) and why.  
7. **Key Risks**: Highlight vulnerabilities (e.g., whipsaws in ranging markets).  
8. **Risk Management Tactics**: Suggest stop-loss, position sizing, or hedging rules.  

Format the output with clear headers and bullet points. "*  



### **Follow-Up Workflow**  
After this example, proceed with:  
1. **Trend Following**  
2. **Momentum**  
3. **Breakout**  
4. **Volatility Targeting**  

Let me know which category to expand next!


