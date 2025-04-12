
# Prompts and Examples

## Overview

This document provides a collection of sample prompts that can be used with generative AI tools to spark ideas, draft code, and refine research and documentation for our trading strategy development. These examples are intended as starting points for experimentation and collaboration. You can modify these prompts to suit your specific needs and share any successful variations with the team.

---

## 1. Signal Generation Prompts

- **Prompt Example:**  
  "Generate a list of potential technical indicators suitable for identifying oversold conditions in a trending market using daily OHLC data."

- **Expected Output:**  
  A list including common indicators such as Relative Strength Index (RSI), Stochastic Oscillator, MACD histogram divergence, Bollinger Band width, etc., along with brief descriptions of how each might be used.

---

## 2. Strategy Logic Prompts

- **Prompt Example:**  
  "Write pseudocode for a mean reversion strategy that enters a long position when the RSI drops below 30 and then crosses back above 30, with exits defined by a fixed profit target and a stop loss."

- **Expected Output:**  
  Pseudocode outlining the steps for checking conditions, placing entry orders, and managing risk through defined exit criteria.

---

## 3. Documentation and Content Refinement Prompts

- **Prompt Example:**  
  "Review and improve the following Markdown text to ensure clarity and consistency with our team style guidelines. Highlight any areas that might need further discussion or modification:  
  'Our strategy framework integrates modular components for entry, exit, and risk management.'"

- **Expected Output:**  
  A revised version that might include clear headings, bullet lists, and highlighted areas for team review using `<mark>` tags, for example:
  

  Our **Strategy Framework** integrates modular components for:
  - **Entry Rules:** Conditions based on indicators or chart patterns.
  - **Exit Rules:** Predefined profit targets and stop-loss levels.
  - **Risk Management:** Position sizing and drawdown controls.
  
  <mark>Note: Review the risk management parameters for consistency with recent performance metrics.</mark>


---

## 4. Code Prototyping Prompts

- **Prompt Example:**  
  "Draft a Python code snippet that uses pandas to load historical stock data from a CSV file, calculate the 14-day RSI, and plot both the RSI and the stock price using matplotlib."

- **Expected Output:**  
  A code snippet similar to:
  
  ```python
  import pandas as pd
  import matplotlib.pyplot as plt
  import talib

  # Load historical data
  data = pd.read_csv('historical_data.csv', parse_dates=['Date'], index_col='Date')
  close = data['Close']

  # Calculate the 14-day RSI
  rsi = talib.RSI(close, timeperiod=14)

  # Plot the close price and RSI
  plt.figure(figsize=(12, 6))
  plt.subplot(2, 1, 1)
  plt.plot(close, label='Close Price')
  plt.legend()
  
  plt.subplot(2, 1, 2)
  plt.plot(rsi, label='14-Day RSI', color='orange')
  plt.axhline(70, color='red', linestyle='--')
  plt.axhline(30, color='green', linestyle='--')
  plt.legend()
  
  plt.show()
  ```

---

## 5. Brainstorming and Strategy Enhancement Prompts

- **Prompt Example:**  
  "Suggest three ways to incorporate volatility filters into a trend-following strategy to reduce false breakouts."

- **Expected Output:**  
  Ideas such as:
  - Implementing an ATR (Average True Range) filter to adjust trade entry thresholds.
  - Utilizing Bollinger Bands to confirm that price breaks are significant.
  - Filtering out signals during periods of extremely low volatility to avoid noise.

---

## Best Practices for Crafting AI Prompts

- **Be Specific:**  
  Provide clear context and desired outcomes. For example, mention data types, timeframes, or specific strategy elements.

- **Iterate and Refine:**  
  Experiment with rephrasing and additional details to see how AI responses evolve. Adjust prompts based on feedback and testing results.

- **Validate Output:**  
  Always cross-check AI-generated responses against your own analysis and backtesting to ensure they are practical and aligned with our strategies.

- **Document Successful Prompts:**  
  Maintain a shared record of prompts that yield useful results in this document. Encourage team members to contribute their variations to continuously enhance our collective resource.

---

## How to Use This Document

- **Reference During Development:**  
  When starting a new signal or strategy development project, revisit these prompts for inspiration and guidance.
- **Collaborate and Improve:**  
  Share your own prompt modifications and outcomes in team meetings or via pull requests to this document.
- **Continuous Update:**  
  As new techniques and insights emerge, update this file to reflect improved methods and best practices.

---

**Conclusion**

Leveraging generative AI can dramatically speed up our research and development process. By using well-crafted prompts, we can generate novel ideas, draft code, and streamline our documentation. Use this document as a baseline to experiment, refine, and collaboratively elevate the quality of our trading strategies.
