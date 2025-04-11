

# Getting Started

Welcome to the **Algorithmic Strategy Development** project! This guide will walk you through the **initial setup** steps so you can start exploring, collaborating, and contributing to the repository.

---

## 1. Cloning the Repository with GitHub Desktop

If you’ve **never used Git or GitHub before**, **GitHub Desktop** offers a simple, graphical way to get the repository onto your local machine.

### 1.1 Install GitHub Desktop

1. **Download**  
   - Visit the [GitHub Desktop website](https://desktop.github.com/) and download the installer.

2. **Install**  
   - Run the installer and follow any on-screen prompts.  
   - Once installed, **sign in** with your GitHub account (create one if you haven’t already).

### 1.2 Clone the Repository in GitHub Desktop

1. **Open GitHub Desktop**  
   After installation, launch GitHub Desktop.  

2. **Clone a Repository**  
   - In the top-left corner, click **File → Clone repository**.  
   - Select **URL** from the options, then paste the repository URL, for example:  
     ```
     https://github.com/etradeteam/strategy_development.git
     ```
   - Choose a local folder (on your computer) where you’d like the repository to live.  
   - Click **Clone**.

3. **Verify the Folder**  
   - Once the cloning is complete, open your chosen folder. You should see files and subdirectories like `Tools`, `Process`, `Team`, `genai`, and others.  
   - Now you can view and edit the repository files locally.

---

## 2. Set Up Your Environment

Depending on the trading platforms or data analysis tools you plan to use, here are the basics:

1. **Code Editor**  
   - [Visual Studio Code](https://code.visualstudio.com/), Atom, or another IDE works well.  
   - See [Tools/vs_code.md](./Tools/vs_code.md) for suggested extensions and workflow tips.

2. **Trading Platform**  
   - Common retail options include **TradeStation** (EasyLanguage), **MultiCharts** (PowerLanguage), or **NinjaTrader** (C#).  
   - Ensure your chosen platform has the historical data and integration features you need.

3. **Data Feeds**  
   - If you plan on doing local backtests, make sure you have a good source for historical OHLC, volume, or tick data.  
   - Check your platform documentation or a reputable data vendor for instructions.

4. **Optional: Python or R**  
   - If you’d like to incorporate advanced analysis or machine learning, install [Python](https://www.python.org/) or R.  
   - Not strictly necessary for straightforward EasyLanguage or C# coding.

---

## 3. Explore the Repository

### 3.1 Documentation & Folder Structure

- **[README.md](./README.md)**  
  Overview of how we develop, test, and deploy trading strategies.  
- **[Kevin_Davey’s_Strategy_Factory.md](./Kevin_Davey%27s_Strategy_Factory.md)**  
  Summary of Kevin Davey’s multi-step approach to systematic trading.  
- **[strategy_categories.md](./strategy_categories.md)**  
  Explores various strategy types (Trend Following, Mean Reversion, Momentum, etc.).

> For a full breakdown, see the [Repository Structure](./README.md#repository-structure) in the main README.

### 3.2 Process Folder

- **[our_process.md](./Process/our_process.md)**  
  End-to-end development pipeline (from idea to live deployment).  
- **[feasibility_testing.md](./Process/feasibility_testing.md)** / **[rigorous_test.md](./Process/rigorous_test.md)**  
  Show how we conduct backtesting, parameter optimization, walk-forward, and Monte Carlo analysis.

### 3.3 Tools Folder

- **[github.md](./Tools/github.md)**  
  Deeper guidance on GitHub workflows, branches, pull requests, and merge conflicts.  
- **[markdown_cheatsheet.md](./Tools/markdown_cheatsheet.md)**  
  Handy syntax for headings, lists, links, and tables in `.md` files.

### 3.4 Team Folder

- **[team_roles.md](./Team/team_roles.md)**  
  Describes various roles (chartist, developer, tester) and responsibilities.  
- **[contribution_based_rewards.md](./Team/contribution_based_rewards.md)**  
  Explains how contributors earn monthly access to strategy repos and data.

### 3.5 genai Folder

- **[README.md](./genai/README.md)**  
  Introduces how we use Generative AI to brainstorm new indicators, signals, or code approaches.  
- **[best_practices.md](./genai/best_practices.md)**  
  Guides on avoiding overfitting and integrating AI outputs responsibly into trading logic.

---

## 4. Begin Your First Contribution

1. **Create or Switch Branches in GitHub Desktop**  
   - Click the branch dropdown in the top bar to create a new branch (e.g., `feature/my_idea`).  

2. **Implement or Modify a Strategy**  
   - Try updating a documentation file or experiment with a strategy script.  
   - Commit changes in GitHub Desktop with a clear description of what you did.

3. **Push Your Changes**  
   - Click **Publish branch** to push it to GitHub.  

4. **Open a Pull Request**  
   - On GitHub, find your branch and create a pull request (PR) into the `main` branch.  
   - Add a short summary, link any relevant issues, and request feedback.

5. **Review & Merge**  
   - Collaborators can comment on your PR. Once approved, merge your changes! 

---

## 5. Next Steps

- **Check Out the Strategies**  
  Refer to [strategy_categories.md](./strategy_categories.md) for details on different strategy philosophies.  
- **Run Initial Tests**  
  If you have a new idea, see [feasibility_testing.md](./Process/feasibility_testing.md) for quick ways to see if it’s viable.  
- **Join the Discussion**  
  Our main communication channels (Discord, Zoom) are listed in [Tools/README.md](./Tools/README.md).

---

## 6. Need Help?

- **Open an Issue**  
  If you’re stuck or have a question, open an issue on GitHub so the team can assist.  
- **Ask a Team Lead**  
  See [team_roles.md](./Team/team_roles.md) to find experts on backtesting, indicators, or coding.

---

**That’s it!** You’re now ready to dive into algorithmic strategy development. Thank you for joining us, and we look forward to seeing your ideas and contributions take shape.