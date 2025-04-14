# Algorithmic Strategy Development

## Welcome to Our Proprietary Trading Team

We are a **collective of passionate traders, quantitative researchers, and technologists**, all **students of Kevin Davey’s Strategy Factory course**, working together to **innovate and refine algorithmic trading strategies**. Our approach is fully collaborative—**every aspect of strategy development** is a team effort, and the resulting strategies are made available to all members. This structure allows each participant to **apply their core strengths**—from chart analysis to advanced coding—so that we collectively enhance our trading edge in today’s dynamic markets.

## How we work together

The objective of our collaborative effort is to systematically organize and divide the strategy development space, allowing us to complement rather than duplicate each other's work. This enables you to focus deeply on specific problems—such as developing Trend Following strategies or refining Money Management methods—with confidence that other team members are concurrently addressing different aspects of the overall strategy space. By clearly defining areas of responsibility and expertise, each team member's efforts are significantly amplified, leading to more efficient progress and higher-quality outcomes.

## Getting Started

 - [Table of Contents](TOC.md): Navingation Page
 - Review the documents in the [Team](team/README.md) directory to get an understanding of **how we work together**.
 - Review the [Onboarding](team/onboarding_guide.md): Includes overview of tools the team uses.
 - [Team Collaboration](team/collaboration.md)
 - Take a look at the [Strategy Process](process/README.md) Documents
 
 ---

# Strategy Development Repository Overview

This is the **Algorithmic Strategy Development** repository. This project aims to provide a structured process and clear documentation for designing, implementing, and testing automated trading strategies suitable for retail traders on platforms like TradeStation, MultiCharts, or NinjaTrader.

## Team Meetings & Communication

- **Weekly Zoom Meetings**  
  - We’ll hold a **weekly Zoom call** to review progress, discuss challenges, and share insights.  
  - Team Standing Zoom Meeting:  
    - https://us06web.zoom.us/j/89104314021?pwd=3KjpJMoCczBkuZYgmCj9AbQAklJwGm.1
    - Meeting ID: `891 0431 4021`
    - Passcode: `275719` 
- **Shared Calendar** - TBD
  - Check the shared calendar or Discord for meeting times and reminders.  
- **Discord Channel**  
  - Daily communication and quick questions can be handled in our dedicated channel.  
  - Feel free to post code snippets, screenshots, or link to references there.

## Team Skill Sets

We’re leveraging multiple perspectives and talents to ensure each strategy benefits from a **diverse range of expertise**. Below are the primary skillsets:

1. **Chartists**  
   - Analyze price action visually.  
   - Identify potential patterns, support/resistance zones, and trend structures.  
   - Provide the “art” of chart reading to complement systematic ideas.

2. **Indicator Developers**  
   - Research and refine technical indicators (moving averages, RSI, Bollinger Bands, custom scripts).  
   - Optimize indicator parameters and test their robustness across market regimes.

3. **Strategy Coders**  
   - Translate trading logic into code (e.g., EasyLanguage for TradeStation, C# for NinjaTrader).  
   - Implement entry/exit rules, manage data feeds, and ensure efficient backtesting.  

4. **Strategy Framework Developers**  
   - Build or enhance our overarching framework to streamline testing, optimization, and reporting.  
   - Maintain version control, integrate new libraries, and manage data pipelines.  

5. **Money Management & Risk Specialists**  
   - Design position-sizing algorithms and risk overlays (e.g., ATR-based sizing, drawdown controls).  
   - Work with developers to integrate robust money management rules into each strategy.

## Strategy Segmentation

We will investigate **strategies** in a range of categories (e.g., Trend Following, Mean Reversion, Breakout, etc.). An **outline** of this process—including initial idea generation, backtesting, and deployment—can be found in our [Development Process Overview](process/README.md). Additionally, our [Strategy Categories](#) document details each category’s unique approach, typical indicators, and market conditions.

We segment algorithms into high-level **categories** and **subcategories** based on their underlying market philosophy and approach. Each category highlights typical indicators, market conditions, and risk profiles. For example:

- **Trend Following**: Moving Average Crossovers, Price Channels, Ichimoku  
- **Mean Reversion**: RSI Reversion, Bollinger Mean Reversion  
- **Momentum**: Price Momentum, Volume-Weighted Momentum  
- **Breakout**: Volatility Expansion, Opening Range  
- …and more

**Full List**: Visit [strategy_types.md](./process/strategy_types.md) for a comprehensive overview and an expanded list of subcategories, along with the indicators typically used.

## Development Process

Below is a simplified workflow for building and refining a trading strategy:

1. **Idea Generation**  
   - Brainstorm market inefficiencies or technical setups.  
   - Examine historical data or known patterns (e.g., price action, volume surges).
   - See the [Strategy Types](strategy_types.md) for a breakdown and approach for identifying strategy ideas

2. **Data Collection & Analysis**  
   - Gather historical OHLC, volume, or tick data.  
   - Filter relevant features (e.g., indicators, volatility measures).

3. **Strategy Definition**  
   - Define entry/exit rules.  
   - Decide on timeframes (1-min, 5-min, daily) and trading styles (scalping, swing, position).  
   - Establish risk management criteria (stop-loss, position sizing).

4. **Backtesting & Optimization**  
   - Run initial backtests to see if the hypothesis holds.  
   - Optimize parameters (e.g., moving average lengths) with caution to avoid overfitting.

5. **Walk-Forward & Out-of-Sample Testing**  
   - Validate the strategy on different time periods to ensure robustness.  
   - Adjust rules or indicators if performance is subpar.

6. **Deployment**  
   - Implement on a trading platform (TradeStation, MultiCharts, NinjaTrader).  
   - Monitor real-time performance and risk.

7. **Monitoring & Iteration**  
   - Regularly evaluate the strategy’s drawdowns, win rates, and risk profile.  
   - Adapt to changing market conditions.

---

# **Repository Organization**

## SD Repository (this repository)

[Table of Contents](TOC.md): Navingation Page

 - [Strategy Development Process](process/README.md): The Strategy Factory Process & our collaborative development process
 - [Resources](resources/README.md): Links to resources such as spreadsheets, strategy ideas, etc
 - [Signals](signals/README.md): Collated list of Signals
 - [Strategy Categories](strategy_categories/README.md):  Strategies are divided into categories.  Each category has a different approach to developing successful strategies.
 - [Team](team/README.md): How do we work as a team.  How can you best utilize your skills.
 - [Tools](tools/README.md): Tools use along with documentation or instructions
 - [Generative AI](genai/README.md): Guidance, prompts, 
 - [Metrics](metrics/README.md): How do we measure strategy success

Other directories:
 - [imgs](imgs): images included in the documentation
 - [docs](docs): documents shared

## Other Repositories

Much of the team work is divided into a number of other repositories.  This strategy development repository describes the overall process.  However, research and development of strategies and core capabilities is divided into a number of additional repositories.

**Core Capabilities**

- [`strategy_framework`](https://github.com/etradeteam/strategy_framework): Shared code modules and utilities for building, testing, and deploying trading strategies (signal logic, execution layer, etc.).
- [`money_management`](https://github.com/etradeteam/money_management): Position sizing, stop-loss/target models, trade filters, and other money and risk management components.
- [`portfolio_management`](https://github.com/etradeteam/portfolio_management): Portfolio Managmenet techniques and resources

**Strategy Categories**

- [`trend_following`](https://github.com/etradeteam/trend_following): Strategies that aim to follow long-term directional market trends using moving averages, ADX, and other trend filters.
- [`breakout`](https://github.com/etradeteam/breakout): Strategies focused on detecting and trading breakouts from consolidation patterns, volatility compressions, or key levels.
- [`momentum`](https://github.com/etradeteam/momentum): Strategies based on price momentum, relative strength, and persistent directional moves across markets or symbols.
- [`mean_reversion`](https://github.com/etradeteam/mean_reversion): Strategies that exploit statistical reversion to mean price levels, Bollinger bands, or RSI extremes.
- [`market_sentiment`](https://github.com/etradeteam/market_sentiment): Strategies driven by crowd psychology, volume spikes, sentiment indicators, or order book imbalances.

**Research**

- [`machine_learning`](https://github.com/etradeteam/machine_learning): Experimental repo for ML-enhanced strategies, including feature engineering, model selection, and supervised/unsupervised testing.
