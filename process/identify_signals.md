# Identify Signals

This document describes how we **discover**, **document**, and **prioritize** potential signals for our trading strategies. Signals can be anything that suggests a **potential edge**—from a simple moving average crossover to a complex order-flow metric or AI-generated indicator.

---

## 1. Introduction

We encourage all team members to propose new signals or ideas. A **signal** can be:
- A **technical indicator** (e.g., RSI, MACD, Bollinger Bands).  
- A **chart pattern** or **price action** structure (e.g., double bottom, trendline break).  
- A **data-driven pattern** uncovered by analysis, backtests, or machine learning.  
- **Market structure elements** (support/resistance levels, pivot points).  

Signals need to be clearly defined, testable, and recorded in a shared “signal library” so everyone can reference them.

---

## 2. Brainstorming & Research Approaches

1. **Technical Analysis**  
   - Traditional indicators (moving averages, oscillators, etc.)  
   - Candlestick patterns or chart formations  
   - Seasonal tendencies or cycles  

2. **Data-Driven Insights**  
   - Statistical analyses (e.g., autocorrelation, lead-lag relationships)  
   - Machine learning feature importance (which inputs best predict short-term moves?)  
   - Volume profiling or order book data (if available)

3. **Fundamental & News Catalysts** (Optional)  
   - Earnings surprises or macroeconomic announcements  
   - Sentiment data (put/call ratios, social media sentiment)  
   - Analyst upgrades/downgrades  

4. **Market Structure Signals**  
   - Identifying major swing highs/lows, support/resistance, trendlines  
   - Detecting channels, triangles, or other geometric patterns  

5. **AI-Generated Concepts**  
   - Brainstorm signals with Large Language Models (LLMs) or specialized AI frameworks.  
   - Validate them carefully to avoid “AI hype” that lacks tangible data support.

---

## 3. Recording & Organizing Signals

1. **Signal Library**  
   - We maintain a centralized tracking system—such as a **spreadsheet** or `.md` file—that includes:  
     - **Name** of the signal  
     - **Description** (what it does, how it’s calculated)  
     - **References** (where it came from: research paper, discussion, etc.)  
     - **Initial Test Results** (if any)  

2. **Versioning**  
   - When you update or refine a signal, create a **new entry** or mark the changes in our library.  
   - This ensures we keep a **historical record** of each signal’s development.

3. **Prioritization**  
   - Not all signals are created equal. Some may only work in certain markets or timeframes.  
   - Label signals (e.g., **“high potential,” “experimental,” “rejected”**) based on preliminary tests or team consensus.

---

## 4. Manual vs. Automated Identification

1. **Manual Identification**  
   - Chartists often spot patterns or recurring behaviors visually.  
   - Keep track of these observations and cross-check with data for confirmation.

2. **Automated Scans**  
   - Use trading platforms (e.g., TradeStation RadarScreen, MultiCharts, or NinjaTrader analyzers) to **scan** for events (e.g., RSI < 30, price crossing moving average).  
   - Write short scripts to sift through historical data for potential patterns or anomalies.

3. **Hybrid Approach**  
   - Combine manual expertise with **automatic scanning** to confirm or disprove subjective observations.  
   - This synergy often leads to stronger signals.

---

## 5. Basic Validation

Before a signal moves forward into strategy development, perform a **quick check**:

1. **Historical Frequency**  
   - Does the signal occur often enough to matter?  
   - Overly rare signals (e.g., triggered once or twice a year) might be less reliable or too slow to test.

2. **Directional Bias**  
   - Check if the signal reliably indicates bullish/bearish moves over a broad data set.  
   - If the signal is random or contradictory, we can discard it quickly.

3. **Market & Timeframe Fit**  
   - Some signals are specifically built for intraday futures while others suit daily stock charts.  
   - Clarify where each signal is intended to work best.

**If a signal shows promise**, we move to the next stage: combining signals into a coherent strategy (see [strategies.md](./strategies.md)).

---

## 6. Tips for Effective Signal Proposals

- **Keep it Simple**: A straightforward idea (e.g., RSI oversold) is easier to test and refine than a 5-layer logic chain.  
- **Reference Real Data**: Provide quick stats (win rate, average drawdown) from a small sample if possible.  
- **Document Clearly**: Others should be able to replicate your signal logic without confusion.  
- **Stay Open-minded**: Even “unlikely” signals can yield an edge if proven by data.

---

## 7. Next Steps

1. **Explore Our Signal Library**  
   - Check out existing signals in the shared tracking file or repository.  
   - Avoid duplicating a signal that’s already well-tested.

2. **Propose New Signals**  
   - Submit ideas via a GitHub issue or in your branch with a new entry in the library (and possibly a script).

3. **Combine Signals**  
   - Once a signal proves interesting, see [strategies.md](./strategies.md) to learn how to integrate it into a broader strategy framework.

---

**Conclusion**: Identifying signals is the critical first step in our trading pipeline. By maintaining a common library and applying basic validation, we ensure **everyone** on the team can leverage the best insights in building robust, data-driven trading strategies.