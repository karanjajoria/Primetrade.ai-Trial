# Quick Start Guide

Get **Primetrade.ai** running in minutes!

## 🚀 5-Minute Setup

### Option 1: Windows PowerShell (Fastest)

```powershell
# Clone repository
git clone https://github.com/yourusername/Primetrade.ai.git
cd Primetrade.ai

# Setup environment (one command)
python -m venv env; .\env\Scripts\Activate.ps1; pip install -r Requirement.txt; pip install jupyter

# Launch analysis
jupyter notebook
# Then open Scripts/check.ipynb and run cells!
```

### Option 2: macOS/Linux

```bash
git clone https://github.com/yourusername/Primetrade.ai.git
cd Primetrade.ai
python -m venv env
source env/bin/activate
pip install -r Requirement.txt
pip install jupyter
jupyter notebook
```

### Option 3: Using Conda

```bash
git clone https://github.com/yourusername/Primetrade.ai.git
cd Primetrade.ai
conda create -n primetrade python=3.10
conda activate primetrade
conda install jupyter pandas numpy scipy seaborn matplotlib
jupyter notebook
```

## 📊 Run the Analysis

1. **Jupyter opens automatically** → Navigate to `Scripts/check.ipynb`
2. **Run all cells** → Shift + Enter (or Shift + Ctrl + Enter to run all)
3. **View results** → Charts, tables, and statistical analysis appear below each cell
4. **Modify and experiment** → Change parameters and re-run to explore

## 📁 What You'll See

| Item | Purpose |
|------|---------|
| **Dataset/** | Raw CSV files (10K+ trades, 7 years data) |
| **Scripts/check.ipynb** | Complete analysis notebook |
| **README.md** | Full documentation |
| **Requirement.txt** | Python dependencies |

## ⚡ Key Findings (What to Look For)

When you run the notebook, look for:

1. **📈 6 Visualization Figures**
   - PnL distribution by sentiment
   - Win rate trends over time
   - Trader performance heatmaps
   - Correlation analysis

2. **📊 Statistical Summary**
   ```
   Fear Regime  → Best avg PnL ($X per trade)
   Greed Regime → Worst performance
   Correlation  → r = -0.3, p < 0.001
   ```

3. **🎯 Key Insight**
   ```
   "Traders consistently outperform during fear periods"
   ```

## 🐛 Troubleshooting

### Issue: `ModuleNotFoundError: No module named 'pandas'`
```bash
pip install -r Requirement.txt
```

### Issue: `jupyter: command not found`
```bash
pip install jupyter notebook
```

### Issue: Virtual environment not activating
**Windows:**
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
.\env\Scripts\Activate.ps1
```

**macOS/Linux:**
```bash
source env/bin/activate
```

### Issue: Cells won't run
- Make sure you're in the correct notebook (`Scripts/check.ipynb`)
- Verify virtual environment is active
- Restart kernel: `Kernel → Restart` in Jupyter menu

## 📚 Next Steps

1. **Explore the analysis** → Modify visualizations and parameters
2. **Read the docs** → Check [README.md](README.md) for detailed sections
3. **Contribute** → See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines
4. **Ask questions** → Open a [Discussion](../../discussions)

## 💡 Tips

- **Save work**: Click `File → Save` in Jupyter to save your notebook
- **Restart clean**: `Kernel → Restart & Clear Output` to reset
- **Edit cells**: Double-click any cell to edit code or markdown
- **Add notes**: Insert new cells with `Insert → Cell`

## 🎓 What Each Notebook Section Does

| Section | What It Shows |
|---------|--------------|
| **Data Prep** | Loads and cleans datasets |
| **EDA** | Distribution of trades by coin/sentiment |
| **Performance** | PnL and win rate by sentiment |
| **Time Series** | Trends over 7+ years |
| **Per-Trader** | Individual trader sensitivity |
| **Statistics** | Correlation tests and ANOVA |
| **Conclusion** | Key findings and strategy |

## 🚀 Advanced Usage

### Run Specific Cells Only
In Jupyter, click any cell and press Shift+Enter to run just that cell.

### Export Results
```python
# In a notebook cell:
import json
results = {
    'best_sentiment': 'Fear',
    'correlation': -0.3
}
with open('results.json', 'w') as f:
    json.dump(results, f)
```

### Modify Data
Edit the CSV paths in cell 2 to use your own trading data:
```python
hist_data = pd.read_csv('path/to/your/data.csv')
```

## ✅ Verification Checklist

After setup, verify everything works:

- [ ] Virtual environment activated
- [ ] All packages installed (`pip list`)
- [ ] Jupyter opened successfully
- [ ] Notebook loads (`Scripts/check.ipynb`)
- [ ] All cells run without errors
- [ ] Charts and tables display
- [ ] Statistical results show correlation and p-values

## 💬 Need Help?

- **Bug?** → [Open an Issue](../../issues)
- **Question?** → [Start a Discussion](../../discussions)
- **Contribution?** → See [CONTRIBUTING.md](CONTRIBUTING.md)

---

**Happy analyzing!** 🎯📊✨
