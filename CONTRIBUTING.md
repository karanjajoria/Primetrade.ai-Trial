# Contributing to Primetrade.ai

Thank you for your interest in contributing! This document provides guidelines and instructions for contributing to the project.

## Code of Conduct

Be respectful, inclusive, and collaborative. Treat all contributors with dignity and respect.

## Getting Started

### Prerequisites
- Python 3.8+
- Git
- Jupyter Notebook (recommended)
- Virtual environment (`venv` or `conda`)

### Setup Development Environment

```bash
# Clone your fork
git clone https://github.com/yourusername/Primetrade.ai.git
cd Primetrade.ai

# Create virtual environment
python -m venv env
source env/bin/activate  # On Windows: .\env\Scripts\activate

# Install dependencies
pip install -r Requirement.txt

# Optional: Install development tools
pip install jupyter notebook pytest black flake8
```

## How to Contribute

### 1. Fork the Repository
Click the "Fork" button on GitHub to create your own copy of the repository.

### 2. Create a Feature Branch
```bash
git checkout -b feature/your-feature-name
# or
git checkout -b fix/bug-name
```

### 3. Make Changes
- Keep commits focused and atomic
- Write clear commit messages
- Follow PEP 8 style guidelines
- Add comments for complex logic

### 4. Test Your Changes
```bash
# Run your notebook cells to ensure they work
jupyter notebook

# Check code style
flake8 Scripts/
```

### 5. Commit and Push
```bash
git add .
git commit -m "Add brief description of changes"
git push origin feature/your-feature-name
```

### 6. Create a Pull Request
1. Go to the original repository
2. Click "New Pull Request"
3. Select your branch
4. Provide a clear description of your changes
5. Link any related issues (e.g., "Fixes #123")

## Guidelines

### Code Style
- Follow [PEP 8](https://www.python.org/dev/peps/pep-0008/) conventions
- Use meaningful variable names
- Add docstrings to functions and classes
- Keep lines under 100 characters

### Jupyter Notebooks
- Clear, logical cell organization
- Include markdown cells explaining sections
- Add comments in code cells
- Use meaningful variable names
- Avoid leaving debug prints or test code

### Commit Messages
```
[Type] Brief description (50 chars max)

Optional detailed explanation (wrap at 72 chars)
- Use bullet points for multiple changes
- Reference issues if applicable (Fixes #123)
```

**Types**: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`

Example:
```
feat: Add sentiment distribution pie chart

- Implemented pie chart showing sentiment day distribution
- Uses color coding from SENT_COLORS palette
- Fixes #42
```

### Documentation
- Update README.md if adding features
- Document new analysis sections
- Include docstrings in Python code
- Add inline comments for complex logic

## Types of Contributions

### 🐛 Bug Fixes
- Report bugs in Issues
- Include:
  - Python version
  - Steps to reproduce
  - Expected vs actual behavior
  - Error messages/tracebacks

### ✨ New Features/Analyses
- Discuss in Issues before major work
- Align with project scope
- Add appropriate tests
- Update documentation

### 📚 Documentation
- Improve clarity and completeness
- Add examples where helpful
- Fix typos and grammatical errors
- Improve tutorial/setup instructions

### 📊 Data Enhancements
- New sentiment indicators
- Additional datasets
- Improved data validation
- Performance optimizations

### 🤖 ML/Analytics
- Predictive models
- New statistical tests
- Advanced visualizations
- Time series analysis

## Pull Request Process

1. **Update your branch**: `git pull origin main`
2. **Ensure tests pass**: Run notebook cells successfully
3. **Check code style**: Follow PEP 8 guidelines
4. **Write PR description**: Be clear and detailed
5. **Be responsive**: Address feedback and comments
6. **Sign commits**: Use verified commits if possible

### PR Checklist
- [ ] Code follows style guidelines
- [ ] Comments added for complex logic
- [ ] README updated (if needed)
- [ ] No new warnings generated
- [ ] Tests/cells run without errors
- [ ] Commit messages are clear

## Community

### Questions or Discussion?
- Open a [GitHub Discussion](../../discussions)
- Join our community
- Reach out respectfully

### Recognition
All contributors will be recognized in the project. We appreciate your time and effort!

## License
By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Happy Contributing!** 🚀
