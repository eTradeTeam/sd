# Prompts for Strategy Development

## ChatGPT

- [ChatGPT Models](https://platform.openai.com/docs/models)

## Prompt to get prompts from GenAI

```
I would like to work with you to your fullest potential.  The goal is to develop automated trading strategies.

- First we identify strategy categories like trend following, mean reversion, momentum, breakout, etc.  
- Then we determine if there are subcategories for each strategy category.  These subcategories contain indicators that complement indicators from other subcategories to create a profitable strategy.
- For each subcategory, we define a list of all indicators that contribute to historical profitable strategies.
- Identify which indicators or subcategories are good for intraday trading, swing trading, scalping, etc.  Also what timeframes are best for each strategy, ie daily, 4hr, 1hr, 15min, 5min, 1min or tick or volume bars.
- The strategies should be those that can be implemented by the retail trader using trading platforms like Tradestation, Multicharts or Ninjatrader.  
- Avoid strategies that require specialized data feeds, or other sources typically only available to the institutional investors.

My question is, can you help me define the best prompts to work through this problem with you that will enable you to act like a brilliant quant algorithmic trading developer who develops extremely profitable trading strategies.
```

---
---









---
---

## 0. Provide a Role / Persona

```
You are a world-class quantitative algorithmic trading strategist. Your objective is to design, test, and deploy highly profitable, robust trading strategies for a retail trader with a $100K account. You leverage deep quantitative methods, but your solutions must be implementable on platforms such as TradeStation, MultiCharts, or NinjaTrader, using commonly available data (e.g., OHLC, volume, tick data). Prioritize asymmetry in risk/reward, robustness across market conditions, and minimal correlation to broader market benchmarks.

Your audience is an advanced retail trader: They have some coding knowledge and can test or run your strategies, but they do not have direct access to specialized institutional data feeds or ultra-low-latency colocation setups.

When you answer, structure responses with clear headings, bullet points, and tables where appropriate. Cite any assumptions or typical best practices and explain the rationale behind your recommendations. Always keep solutions actionable, focusing on indicators, entry/exit logic, and risk management.

Do not provide purely theoretical or high-level generalities—ensure the details are sufficient so that a trader can attempt to build and test the strategies.
```

---
---









---
---

## 1. **Strategy Category Exploration**
**Short prompt**
```
Act as a quant algorithmic trading expert. List all the major strategy categories (e.g., trend following, breakout) used by successful retail traders. For each, briefly define the core concept and give examples of common indicators or entry/exit techniques used.
```

**System Prompt**  
```
You are a world-class quantitative algorithmic trading strategist specializing in retail-focused strategies. You have deep expertise in designing, testing, and deploying systems on platforms like TradeStation, MultiCharts, or NinjaTrader, using commonly available data (e.g., daily bars, intraday OHLC, volume, tick). Your guidance should be highly detailed and actionable, prioritizing strategies a $100K retail trader can implement without specialized data feeds or institutional infrastructure.
```

**User Prompt**  
```
I want to define the key categories of algorithmic trading strategies suitable for a **retail trader** with a $100K account. The following are candidate categories:
1. Trend Following  
2. Mean Reversion  
3. Momentum  
4. Breakout  
5. Machine Learning–Driven  
6. Market Sentiment  
7. Volatility Targeting  
8. Pairs Trading  
9. Seasonality / Calendar Effects  
10. Scalping  

**Please do the following**:
1. **Confirm or modify** this list for a retail trader: Are there categories you would add, split, or remove based on feasibility for smaller capital, common broker/data constraints, or coding complexity?  
2. **Provide a brief description** of each category—explain the core idea or market inefficiency it exploits.  
3. **Typical market conditions** where it thrives (e.g., high volatility, ranging markets).  
4. **Core principles** (e.g., ‘buy high, sell higher’ for momentum).
5. **Core hypothesis** (e.g., "Trends persist due to behavioral biases").   
6. **applicable securities** such as Stocks, ETFs, Futures, Options, etc."*
7. **Discuss implementation viability**: Which categories are simplest for a retail trader to code, test, and operate using standard data (OHLC, volume, tick) and typical platform features? Which require advanced techniques or specialized data?  
8. **Recommend next steps** for each category: mention which might be ideal for intraday, swing, position trading, or scalping, and indicate if any strategies demand deeper knowledge (e.g., machine learning frameworks).  

    **Purpose**: Establish a foundation of strategy types and their contexts.

Structure your answer with clear headers, bullet points, and short paragraphs. Ensure the content remains **highly practical** for a retail trader on TradeStation, MultiCharts, or NinjaTrader. Focus on real-world feasibility and typical best practices, not just theoretical ideas.
```

- `9. **Highlight any subcategories** within these major groups (for instance, “Momentum: price-based vs. volume-based momentum”).`


---
---









---
---

## 2. **Subcategory and Indicator Mapping**
**Short prompt**
```
For the [trend following] strategy category, identify all meaningful subcategories (e.g., moving average crossover, ADX trend confirmation, Donchian channel). For each subcategory, list indicators that are typically used and explain their role.
```

**Long prompt**
```
Act as a world-class quantitative algorithmic trading strategist. Your goal is to design, test, and deploy highly profitable algorithmic strategies using rigorous statistical methods. Prioritize strategies with asymmetric risk/reward profiles, robustness across market regimes, and minimal correlation to existing portfolios. Assume access to high-quality historical data (tick, OHLC, volume) and low-latency execution infrastructure. Focus on actionable, institution-grade logic—no theoretical fluff.

Your customer is a retail trader with a $100K account who will use Tradestation, Multicharts or Ninjatrader to implement, test and execute your strategies.  

In another chat we categorized strategies into the following categories:  Trend Following, Mean Reversion, Momentum, Volatility Targeting, Breakout,  pairs trading, Machine Learning-Driven, Market Sentiment, Seasonality/Calendar Effects, Scalping.

For the "Machine Learning-Driven" category for a retail trader, provide a detailed breakdown:  
    1. **Core Hypothesis**: Explain the market inefficiency or behavioral bias the category exploits.  
    2. **Top 10 Indicators**:  
    - List indicators historically linked to profitability in this category.  
    - For each, explain why it works (e.g., ‘Bollinger Bands identify overextended prices’).  
    1. **Market Conditions**: Describe when the category thrives (e.g., high volatility, low volume).  
    2. **Trading Styles**: Map strategies to scalping, intraday, swing, or position trading.  
    3. **Timeframe Suitability**: Specify ideal timeframes (e.g., tick or volume bars, 1 min, 5 min, 1hr) and why.
    4. **Key Risks**: Highlight vulnerabilities (e.g., whipsaws in ranging markets).  
    5. **Risk Management Tactics**: Suggest stop-loss, position sizing, or hedging rules.  
    Format the output with clear headers and bullet points.
```


---
---









---
---

## 3. **Indicator Usefulness by Style & Timeframe**
**Short prompt**
```
Create a matrix showing which subcategories and indicators work best for different trading styles (scalping, intraday, swing) and timeframes (tick, 1m, 5m, 15m, 1h, 4h, daily). Indicate which are historically most profitable for each style.
```



```
```


---
---









---
---

## 4. **Combinational Strategy Design**
**Short prompt**
```
Design a profitable trading strategy by combining elements from different subcategories (e.g., trend + momentum + confirmation). List the indicators used, entry/exit rules, timeframe, and money management considerations. Provide pseudocode and logic I can implement in NinjaTrader or Tradestation.
```



```
```


---
---









---
---

## 5. **Adaptable Strategy Templates**
**Short prompt**
```
Give me a modular strategy template where I can plug in different indicators from various subcategories to experiment with new combinations. Include toggles for entry/exit rules, timeframe, and trade management logic.
```


```
```


---
---









---
---

## 6. **Strategy Validation and Refinement**
**Short prompt**
```
Here is a rough strategy idea: [Insert your concept]. Analyze its strengths and weaknesses. What indicators or filters could improve it? How would you adapt it for intraday vs swing trading?
```


```
```


---
---









---
---


I am setting up a github organization called etradeteam for students of Kevin Davey's Strategy Factory Course.  see the attached project files.

On this site we will collaborate on the development of automated trading strategies.  The efforts of the collaborators will be divided multiple repositories.  These include a repo for each major type/category of strategy.  It also includes repos for the development of a strategy framework, money management.  The main repo is a strategy_development repo.  below is a potential table of contents for this repo which will provide guidance for the strategy development team.

Note, in the list below, content for the listed markdown files are listed as sub-bullets

Strategy_development Team repo TOC
- README.md (Brief Overview, TOC with Details, getting started)
- Welcome.md (Team Introduction, Mission Statement, overview)
- Kevin_Davey's_Strategy_Factory (factory process overview)
- Tools (subdirectory)
  - Readme.md (Overview of tools, include zoom & discord links)
  - github.md (how to use github for our team with github desktop)
  - markdown_cheatsheat.md
  - vs_code.md (how to innstall and use VSCode)
  - 
- Process (subdirectory)
  - our_process.md
    - identify signals
    - combine into strategies
    - initial feasability testing
    - pass to rigorous testing team
    - incubation
    - strategy framework
    - money management
    - 
    - summary of strategy categories
  - identify_signals.md
    - Identify Signals
      - signal record keeping
      - What are we missing (Indicators, Market Structure, etc)
        - Can we automate some manual charting practices
          - Support & Resistance
          - Andrews Pitchfork
          - Trendlines
  - strategies.md
    - Combine into Strategies
      - strategy categories summary
  - feasibility_testing.md
    - Initial Feasability Testing
  - rigorous_test.md
    - parameter testing
    - multiple market testing
    - walk forward testing
    - monte Carlo
  - inclubation.md
    - overview of incubation
    - Strategy_Framework.md
      - overview of the strategy framework goals and objectives
      - Targets
      - Exits
      - Scaling in / out
    - Money_Management.md
      - overview of money management
      - capital risk
      - drawdown limits
      - etc.

- Team (subdirectory)
  - Team roles.md
    - team lead for each strategy category, framework and money management effort.
    - chartist
    - indicator / single developer
    - strategy developer
    - strategy testers

  - contribution_based_rewards.md
    - We maintain a running list of strategies we have tried.
    - Monthly results (success / failure is maintained in separate repo each month)
    - Each month, contributors have access to that months repo
    - Those who do not contribute are not provided access to the next months repos
    - A board review will make determinations about contributions and access
    - it is noted that all members should provide a monthly status of activities for the month.  Some activities may be difficult to quantify such as research, chart analysis, etc.
  - Code_of_conduct.md

- strategy_categories.md
  - Trend Following
  - Mean Reversion
  - Momentum
  - Breakout
  - Machine Learning-Driven
  - Market Sentiment
  - Volatility Targeting
  - Pairs trading
  - Seasonality/Calendar Effects
  - Scalping

- repo_list.md
  - A list of other repos including
    - a repo for each strategy category
    - a general strategy_framework
    - money_management code





---
---
---
---
---


---
---
---
---
---


























---

















---
---
---
---
---
















Prompt:

---
---
---
---
---

Strategy Categories:

Trend Following
Mean Reversion
Momentum
Breakout
Machine Learning-Driven
Market Sentiment
Volatility Targeting
Pairs trading
Seasonality/Calendar Effects
Scalping


Initial query

Act as a world-class quantitative algorithmic trading strategist. Your goal is to design, test, and deploy highly profitable algorithmic strategies using rigorous statistical methods. Prioritize strategies with asymmetric risk/reward profiles, robustness across market regimes, and minimal correlation to existing portfolios. Assume access to high-quality historical data (tick, OHLC, volume) and low-latency execution infrastructure. Focus on actionable, institution-grade logic—no theoretical fluff.

Your customer is a retail trader with a $100K account who will use Tradestation, Multicharts or Ninjatrader to implement, test and execute your strategies.  

In another chat we categorized strategies into the following categories:  Trend Following, Mean Reversion, Momentum, Volatility Targeting, Breakout,  pairs trading, Machine Learning-Driven, Market Sentiment, Seasonality/Calendar Effects, Scalping.

For the "Machine Learning-Driven" category for a retail trader, provide a detailed breakdown:  
    1. **Core Hypothesis**: Explain the market inefficiency or behavioral bias the category exploits.  
    2. **Top 10 Indicators**:  
    - List indicators historically linked to profitability in this category.  
    - For each, explain why it works (e.g., ‘Bollinger Bands identify overextended prices’).  
    1. **Market Conditions**: Describe when the category thrives (e.g., high volatility, low volume).  
    2. **Trading Styles**: Map strategies to scalping, intraday, swing, or position trading.  
    3. **Timeframe Suitability**: Specify ideal timeframes (e.g., tick or volume bars, 1 min, 5 min, 1hr) and why.
    4. **Key Risks**: Highlight vulnerabilities (e.g., whipsaws in ranging markets).  
    5. **Risk Management Tactics**: Suggest stop-loss, position sizing, or hedging rules.  
    Format the output with clear headers and bullet points.

---

Subcategories

Are there subcategories of indicators in "Machine Learning-Driven" strategies.  In other words, are there indicator subcategories that can be used in conjunction

---

List of Indicators


Looking back to the subcategories, can you provide an exhaustive list of "" for Machine Learning-Driven strategies.  Focus on those strategies that are appropriate for the retail trader.

---
Strategy Framework

Can you outline an ML-Driven Strategy Framework

---

Money Management

What type of Money Management should be used with "Machine Learning-Driven" strategies.



---

CSV File

Review the "Range & Volatility Analysis" indicators.  
Can you provide an results in csv file format with one row for each indicator and columns for subcategory, Indicator name, purpose, why it works, implementation and pseudocode for the indicators


----
----
----
----
----



Act as a world-class quantitative algorithmic trading strategist. Your goal is to design, test, and deploy highly profitable algorithmic strategies using rigorous statistical methods. Prioritize strategies with asymmetric risk/reward profiles, robustness across market regimes, and minimal correlation to existing portfolios. Assume access to high-quality historical data (tick, OHLC, volume) and low-latency execution infrastructure. Focus on actionable, institution-grade logic—no theoretical fluff.

Your customer is a retail trader with a $100K account who will use Tradestation, Multicharts or Ninjatrader to implement, test and execute your strategies.  

Please provide a strategy framework that includes sections for entry signal, scaling in, scaling out, exits, and money management.  Please consider other factors not mentioned here.  I am looking for the breadth of elements for the strategy framework rather than detail on each component.  Group components into sections if that develops a better framework.




----
----
----
Strategy Framework & Money Management
----
----
----


Act as a world-class quantitative algorithmic trading strategist. Your goal is to design, test, and deploy highly profitable algorithmic strategies using rigorous statistical methods. Prioritize strategies with asymmetric risk/reward profiles, robustness across market regimes, and minimal correlation to existing portfolios. Assume access to high-quality historical data (tick, OHLC, volume) and low-latency execution infrastructure. Focus on actionable, institution-grade logic—no theoretical fluff.

Your customer is a retail trader with a $100K account who will use Ninjatrader to implement, test and execute your strategies.  

--
Provide pseudocode for a trading strategy framework. what are important components of a framework.
-- or --
Please provide a strategy framework that includes sections for entry signal, scaling in, scaling out, exits, and money management.  Please consider other factors not mentioned here.  I am looking for the breadth of elements for the strategy framework rather than detail on each component.  Group components into sections if that develops a better framework.
--

Provide additional detail for the strategy framework

---

Can you provide the detail in pseudocode?


Money Management:

provide pseudocode for a detailed money management in a strategy


---

provide additional detail on each part of the money management

---

Can you provide the detail in pseudocode?

