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

# Strategy Framework

This file describes our **modular, standardized approach** to implementing trading strategies. By following a common structure for entries, exits, risk management, and position sizing, we can rapidly test new ideas while maintaining code quality and consistency across our entire strategy library.

---

## 1. Overview

1. **Why a Framework?**  
   - Centralizes common components (e.g., stop-loss logic, position sizing) so each strategy doesn’t reinvent the wheel.  
   - Facilitates **faster iteration**, consistent testing, and easier maintenance.

2. **Key Objectives**  
   - **Uniform Code Structure**: All strategies share the same “skeleton,” making them easier to compare and troubleshoot.  
   - **Reusability & Modularity**: One change to a core function (e.g., a trailing stop module) can benefit multiple strategies.  
   - **Scalability**: Supports everything from simple single-signal setups to complex multi-filter strategies.

---

## 2. Core Components

Our framework breaks down trading logic into distinct modules. Each module can be **activated** or **omitted** as needed:

1. **Entry Rules**  
   - Defines the conditions (e.g., technical indicator signals, chart patterns) that trigger new long or short positions.  
   - May include optional filters (time-based, volatility-based) to refine entry.

2. **Exit Rules**  
   - Includes stop-loss, profit targets, or time-based closes.  
   - Can incorporate trailing stops or scaling logic (partial exits along the way).

3. **Risk Management**  
   - Ties directly into [Money_Management.md](./Money_Management.md).  
   - Dictates position sizing (fixed fractional, volatility-based, etc.).  
   - Manages maximum drawdown thresholds, daily loss limits, or forced halts.

4. **Parameter Handling**  
   - Each module typically has parameters (e.g., moving average length, RSI period, stop-loss %).  
   - The framework standardizes how these parameters are defined, stored, and passed between modules.

5. **Trade Management**  
   - Manages active positions (e.g., if a trailing stop updates, it notifies the platform).  
   - Allows for advanced features like scale-in/scale-out or hedging across correlated instruments.

---

## 3. Architecture & Flow

A high-level trading loop often looks like this:

1. **Initialize Parameters**  
   - Read default or user-defined settings (e.g., `MA_Length = 50`, `StopLossPercent = 2%`).

2. **On Bar/Price Update**  
   - **Check Entry Logic**: Evaluate whether signals are triggered or not.  
   - **Check Exit Logic**: If a position is open, see if any exit conditions are met.  
   - **Update Orders**: Submit new orders or modify stop/limit orders as needed.

3. **Risk & Money Management**  
   - For each new trade, calculate position size and ensure no risk thresholds are exceeded.

4. **Logging & Metrics**  
   - Record each signal trigger, fill price, and P/L in real time (or after each bar).  
   - Supply data for performance reporting, to be used in further analysis.

---

## 4. Implementation Guidelines

1. **Platform-Specific Code**  
   - We maintain a similar logical structure in each environment:  
     - **TradeStation/MultiCharts** (EasyLanguage/PowerLanguage): Typically a single `.eld` or `.ela` file per strategy, referencing shared “include” files for common modules.  
     - **NinjaTrader (C#)**: A `.cs` strategy file, referencing classes or partial classes that contain entry/exit modules.

2. **Unified Function Names**  
   - For example, if you build a “CalculateStopLoss” function, keep the same name across all strategies and platforms to promote familiarity.

3. **Parameter Documentation**  
   - In code comments or a separate `.md` file, list each parameter and its range, default value, and purpose.  
   - Consistency reduces confusion about what each parameter does.

4. **Coding Conventions**  
   - Use consistent naming for variables (e.g., `EntryCondition`, `StopLossValue`) and methods (e.g., `CalculatePositionSize()`).  
   - Include version or date tags for easier debugging over time (e.g., `// v1.2 - Updated trailing stop logic`).

---

## 5. Scaling In & Out

1. **Rationale**  
   - Many trading styles benefit from partial entries or exits (e.g., scaling out half the position at +1R gain, then trailing stop on the remainder).

2. **Implementation**  
   - Integrate into the exit module, specifying partial close orders at certain profit thresholds.  
   - Must account for additional transaction costs and complexities in the backtester (especially for intrabar or partial fill logic).

3. **Risk Considerations**  
   - Carefully track how scaling adjusts your overall capital risk.  
   - If scaling in, ensure each increment respects the position sizing rules from [Money_Management.md](./Money_Management.md).

---

## 6. Example Workflow

1. **Signal Definition**  
   - Use a module for RSI or moving average cross.  
   - Parameter: `RSI_Period = 14`.

2. **Entry Module**  
   - Checks if RSI < 30 → Generate long signal.  
   - If a position is not already open, place a buy order.  
   - If it is open, do nothing (or scale in, if your strategy calls for it).

3. **Exit Module**  
   - On each bar, check if RSI > 70 to exit or if a trailing stop is triggered.  
   - Adjust or close positions accordingly.

4. **Risk / Position Sizing**  
   - For each new trade, use `Fixed Fractional` or `Volatility-Based` sizing to determine quantity.  
   - Example: Risk $200 on each trade, so if your stop is $1 away, you buy 200 shares.

5. **Order Execution**  
   - The platform sends your orders to the market (or sim) in real time.  
   - The framework captures fill events and updates P/L tracking.

---

## 7. Best Practices

1. **Modularize**  
   - Keep entries, exits, and risk logic in separate functions/classes for clarity.  
   - Don’t bury your strategy logic in a single huge file if it can be segmented.

2. **Avoid Hardcoding**  
   - Make timeframes, filters, or thresholds **parameter-driven** so you can test variations easily.

3. **Thorough Testing**  
   - Each strategy that uses the framework goes through the standard [feasibility testing](./feasibility_testing.md) → [rigorous test](./rigorous_test.md) → [incubation](./incubation.md) pipeline.

4. **Version Control**  
   - All changes to shared framework modules must go through pull requests on GitHub.  
   - Peer review ensures each change doesn’t inadvertently break an existing strategy.

---

## 8. Future Enhancements

1. **AI/ML Integration**  
   - The framework can accommodate AI-based signals by calling specialized modules or external libraries.  
   - Keep the same structure: AI signals feed into the “Entry” or “Filter” modules.

2. **Multi-Instrument / Portfolio Trading**  
   - Expand the framework to handle scanning or trading multiple symbols simultaneously.  
   - Use a unified approach to position sizing that references total portfolio risk.

3. **Event-Driven Architecture**  
   - Some advanced setups might prefer an event-driven model (e.g., each market tick triggers an evaluation).  
   - The current bar-by-bar approach can be adapted to event-driven with minimal changes to the core logic.

---

## 9. Next Steps

- **Adopt the Framework**  
  - When coding a new strategy, align it with these modules and naming conventions.  
- **Refine & Document**  
  - Keep notes on improvements or new modules needed.  
- **Test Thoroughly**  
  - Ensure each strategy that uses the framework meets acceptance criteria in [rigorous_test.md](./rigorous_test.md) and [incubation.md](./incubation.md).

---

**Conclusion**: A well-designed framework accelerates **strategy development** by promoting **code reusability, consistency,** and **maintainability**. Through common modules for entries, exits, and risk, you can experiment with new ideas swiftly while ensuring every strategy meets your team’s quality and documentation standards.