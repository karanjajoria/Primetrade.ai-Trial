# Primetrade.ai - Sentiment Analysis & Trader Performance

<div align="center">

[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![Data Analysis](https://img.shields.io/badge/Analysis-Crypto%20Trading-brightgreen.svg)]()
[![Status](https://img.shields.io/badge/status-active-success.svg)]()

**Analyzing the Relationship Between Bitcoin Market Sentiment and Trader Profitability**

[Quick Start](#quick-start) • [Installation](#installation--setup) • [Usage](#usage) • [Contributing](#contributing)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Key Findings](#key-findings)
- [Project Structure](#project-structure)
- [Dataset Description](#dataset-description)
- [Quick Start](#quick-start)
- [Installation & Setup](#installation--setup)
- [Usage](#usage)
- [Analysis Sections](#analysis-sections)
- [Key Metrics](#key-metrics)
- [Strategic Implications](#strategic-implications)
- [Technologies Used](#technologies-used)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Overview

**Primetrade.ai** is a data analysis project that investigates the relationship between **Bitcoin market sentiment** (measured by the Fear & Greed Index) and **trader performance** across 32 traders executing crypto derivative trades.

The analysis reveals a **contrarian trading insight**: traders consistently achieve higher profitability and win rates during periods of **extreme fear**, while performance deteriorates during periods of **greed**. This finding aligns with classical contrarian investment wisdom: "Be greedy when others are fearful, and fearful when others are greedy."

## Quick Start

Get up and running in 5 minutes:

```bash
# Clone the repository
git clone https://github.com/yourusername/Primetrade.ai.git
cd Primetrade.ai

# Create and activate virtual environment
python -m venv env
.\env\Scripts\Activate.ps1  # Windows PowerShell
# or
source env/bin/activate     # macOS/Linux

# Install dependencies
pip install -r Requirement.txt

# Launch Jupyter and open Scripts/check.ipynb
jupyter notebook
```

> 💡 **Tip**: Run cells sequentially (Shift + Enter) to reproduce the full analysis

## Key Findings

### 📊 Main Insights

1. **Fear Outperforms Greed**
   - Best average PnL per trade occurs during Fear sentiment regime
   - Worst performance in Greed/Extreme Greed periods
   - Traders capitalize on market panic by entering positions when others retreat

2. **Win Rate Inversely Linked to Greed**
   - Highest win rate during Extreme Fear (~60%+)
   - Lowest win rate during Greed periods (~45%)
   - Overconfidence during greed periods leads to more losing trades

3. **Statistically Significant Relationship**
   - Negative correlation between Fear & Greed Index and daily PnL (r ≈ -0.3)
   - One-way ANOVA confirms sentiment regime significantly explains PnL variance (p < 0.001)

4. **Position Sizing Patterns**
   - Traders reduce position sizes in Extreme Greed
   - Risk management becomes tighter at market peaks
   - Larger positions taken during fear regimes (contrarian positioning)

## Project Structure

```
Primetrade.ai/
├── README.md                      # Project documentation
├── Requirement.txt                # Python dependencies
├── Dataset/
│   ├── historical_data.csv       # Trading records (32 traders)
│   └── fear_greed_index.csv      # Bitcoin Fear & Greed Index (2018-2025)
├── Scripts/
│   └── check.ipynb               # Main analysis notebook
└── env/                          # Python virtual environment
```

## Dataset Description

### Historical Data (`historical_data.csv`)
- **Records**: 10,000+ individual trades
- **Time Period**: 2018 onwards
- **Key Fields**:
  - `Account`: Trader wallet address (anonymized as T1-T32 in analysis)
  - `Timestamp IST`: Trade execution timestamp
  - `Coin`: Cryptocurrency pair traded
  - `Direction`: Trade type (Long/Short - Close Long/Close Short)
  - `Size USD`: Position size in USD
  - `Closed PnL`: Realized profit/loss
  - `Fee`: Trading commission

### Fear & Greed Index (`fear_greed_index.csv`)
- **Records**: 2,500+ daily measurements
- **Time Period**: 2018-2025
- **Key Fields**:
  - `date`: Trading date
  - `value`: Index value (0-100 scale)
  - `classification`: Sentiment category
    - `Extreme Fear` (0-25)
    - `Fear` (25-45)
    - `Neutral` (45-55)
    - `Greed` (55-75)
    - `Extreme Greed` (75-100)

## Installation & Setup

### Prerequisites

- **Python** 3.8 or higher
- **pip** (Python package manager)
- **Git** (for cloning the repository)
- **Jupyter Notebook** (optional but recommended for interactive analysis)

### Step-by-Step Installation

#### 1️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/Primetrade.ai.git
cd Primetrade.ai
```

#### 2️⃣ Create Virtual Environment

```bash
python -m venv env
```

#### 3️⃣ Activate Virtual Environment

**Windows (PowerShell):**
```powershell
.\env\Scripts\Activate.ps1
```

**Windows (Command Prompt):**
```cmd
.\env\Scripts\activate.bat
```

**macOS/Linux:**
```bash
source env/bin/activate
```

#### 4️⃣ Install Dependencies

```bash
pip install -r Requirement.txt
```

**Optional - Install Jupyter:**
```bash
pip install jupyter notebook
```

### Dependencies

| Package | Version | Purpose |
|---------|---------|---------|
| `pandas` | Latest | Data manipulation and analysis |
| `numpy` | Latest | Numerical computing |
| `scipy` | Latest | Statistical functions |
| `seaborn` | Latest | Statistical data visualization |
| `matplotlib` | Latest | Plotting and visualization |

## Usage

### Running the Analysis

1. **Launch Jupyter:**
   ```bash
   jupyter notebook
   ```

2. **Open the notebook:**
   - Navigate to `Scripts/check.ipynb`
   - Run cells sequentially (Shift + Enter)

3. **Notebook Sections:**
   - **Data Loading & Cleaning**: Load and validate datasets
   - **EDA Overview**: PnL distribution, top traded coins, sentiment breakdown
   - **Performance Analysis**: Aggregate metrics by sentiment regime
   - **Time Series Analysis**: Daily PnL trends, cumulative PnL, rolling win rates
   - **Per-Trader Analysis**: Individual trader performance across sentiments
   - **Statistical Tests**: Correlation analysis and ANOVA
   - **Conclusion**: Key findings and strategic implications

### Output
The notebook generates:
- **6+ visualization figures** including histograms, heatmaps, box plots, and time series charts
- **Statistical summary tables** showing PnL, win rates, and trade counts by sentiment
- **Correlation coefficients** and p-values for hypothesis testing

## Analysis Sections

### 1. Data Preparation
- Load trading history and fear/greed index
- Clean null values and format timestamps
- Filter closed trades (Long/Short closures only)
- Merge datasets on date field

### 2. Exploratory Data Analysis (EDA)
- PnL distribution across all trades
- Top 10 most traded coins by volume and profitability
- Sentiment distribution in the dataset
- Overall statistics (win rate, total PnL, trade counts)

### 3. Sentiment-Based Performance
- Aggregate trading metrics by sentiment regime
- Compare profitability, win rates, and position sizes
- Visualize performance differences across sentiments
- Per-trader heatmaps showing individual sensitivity to sentiment

### 4. Temporal Trends
- Daily aggregates with sentiment labels
- Cumulative PnL growth over time
- 7-day rolling win rate with sentiment background coloring
- Correlation between Fear & Greed Index movements and daily PnL

### 5. Trade Direction Analysis
- Long vs Short performance by sentiment
- Win rate comparison across trade directions
- Average PnL differences between longs and shorts

### 6. Statistical Validation
- **Pearson Correlation**: Fear & Greed Index vs Daily PnL
- **Pearson Correlation**: Fear & Greed Index vs Win Rate
- **One-Way ANOVA**: Sentiment regime effect on PnL variance
- Significance testing (α = 0.05)

## Key Metrics

| Metric | Definition |
|--------|-----------|
| **PnL** | Profit and Loss (Closed PnL only) |
| **Win Rate** | Percentage of trades with positive PnL |
| **Sentiment** | Fear & Greed classification (5 categories) |
| **FG Index Value** | Numeric sentiment score (0-100) |
| **Average PnL/Trade** | Mean profit/loss per closed trade |
| **Cumulative PnL** | Total realized profit across all trades |
| **Position Size** | USD value of each trade |

## Strategic Implications

Based on the analysis, traders should:

✅ **DO:**
- Enter positions aggressively during **Extreme Fear/Fear** periods
- Monitor position size carefully during **Greed/Extreme Greed** regimes
- Use sentiment as a risk management signal
- Scale into contrarian positions when index drops

❌ **DON'T:**
- Overtrade during peak greed periods
- Increase leverage when fear index is high
- Ignore sentiment regime shifts
- Maintain uniform position sizes across sentiment conditions

## Technologies Used

- **Data Processing**: pandas, numpy
- **Statistics**: scipy.stats
- **Visualization**: matplotlib, seaborn
- **Notebook**: Jupyter
- **Language**: Python 3.8+

## Notes

- **Anonymization**: Trader addresses are masked (T1-T32) to protect privacy
- **Time Period**: Analysis covers 2018-2025, including multiple market cycles
- **Data Quality**: No significant null values; all datasets aligned on date
- **Statistical Rigor**: All correlations tested for significance (p < 0.05)

## Future Enhancements

- [ ] Implement machine learning models to predict trade outcomes based on sentiment
- [ ] Add risk metrics (Sharpe ratio, maximum drawdown, Sortino ratio)
- [ ] Integrate additional sentiment indicators beyond Fear & Greed Index
- [ ] Backtest contrarian strategy with forward-testing validation
- [ ] Real-time sentiment monitoring dashboard
- [ ] Per-coin sentiment sensitivity analysis
- [ ] Trader clustering based on sentiment preferences

## Author Notes

This analysis demonstrates the power of **contrarian investing principles** in crypto markets. The consistent outperformance during fear periods suggests that disciplined, emotion-free trading aligned with market sentiment contrarianism can be a profitable edge.

---

## Contributing

Contributions are welcome! Whether it's bug reports, feature suggestions, or improvements, we'd love to have your input.

### How to Contribute

1. **Fork the repository** on GitHub
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add some amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request** and describe your changes

### Guidelines

- Follow PEP 8 style guidelines for Python code
- Add comments and docstrings for complex logic
- Update the README if adding new features
- Test your changes before submitting

### Areas for Contribution

- 🐛 **Bug Fixes**: Found an issue? Let us know!
- ✨ **New Analyses**: Add additional statistical tests or visualizations
- 📊 **Data Enhancements**: Integrate new sentiment indicators
- 🤖 **ML Models**: Build predictive models based on sentiment
- 📚 **Documentation**: Improve guides and comments
- 🧪 **Testing**: Add unit tests and validation

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.
```

---

## Contact

Have questions or suggestions? Reach out!

- **GitHub Issues**: [Open an issue](../../issues)
- **Discussions**: [Start a discussion](../../discussions)
- **Email**: [your-email@example.com]

### Acknowledgments

- Fear & Greed Index: [alternative.me](https://alternative.me/crypto/fear-and-greed-index/)
- Data provided by: Trading platform derivatives data
- Statistical methods: SciPy and NumPy communities

---

<div align="center">

**⭐ If you find this project useful, please consider giving it a star!**

Made with ❤️ for the crypto trading community

</div>
