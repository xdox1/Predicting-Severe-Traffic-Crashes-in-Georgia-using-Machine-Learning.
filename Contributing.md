# Contributing to Traffic Accident Severity Prediction

Thank you for your interest in contributing! This document outlines guidelines for reporting issues, proposing changes, and submitting contributions.

---

## Table of Contents

- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Guidelines](#development-guidelines)
- [Code Style](#code-style)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Reporting Issues](#reporting-issues)

---

## Getting Started

1. **Fork** the repository and clone your fork locally:
   ```bash
   git clone https://github.com/your-username/your-fork.git
   cd your-fork
   ```

2. **Install dependencies:**
   ```bash
   pip install pandas scikit-learn matplotlib openpyxl jupyter
   ```

3. **Create a new branch** for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Verify the notebook runs end-to-end** before making any changes:
   ```bash
   jupyter nbconvert --to notebook --execute ML_Project_traffic__1_.ipynb
   ```

---

## How to Contribute

Contributions are welcome in the following areas:

- **Bug fixes** — incorrect predictions, broken cell dependencies, or data loading errors
- **New features** — additional models, alternative feature engineering approaches, or new visualizations
- **Dataset improvements** — expanding beyond Georgia, adding more recent accident records, or enriching with additional columns
- **Documentation** — improving the README, adding inline comments, or writing docstrings
- **Performance** — optimizing preprocessing pipelines or model training time

---

## Development Guidelines

### Notebook Structure

- Maintain the existing cell execution order. Cells must run sequentially without errors on a fresh kernel.
- Do not introduce hidden state — any variable used in a later cell must be defined in an earlier one.
- Restart the kernel and run all cells before submitting to confirm end-to-end reproducibility.

### Adding New Models

If you are adding an alternative classifier or comparing multiple models:

- Train and evaluate in a clearly labeled new cell or section.
- Use the same `StandardScaler` fitted on training data — do not refit on the full dataset or test set.
- Report at minimum: accuracy, precision, recall, F1-score, and confusion matrix.

### Forecasting Changes

If modifying the future forecasting methodology:

- Document any assumptions (e.g., representative hour, median imputation strategy) with inline comments.
- Ensure the output `DataFrame` still contains `Start_Time` and `Predicted_Severe_Prob` columns so downstream cells remain compatible.

---

## Code Style

- Follow [PEP 8](https://peps.python.org/pep-0008/) conventions for Python code.
- Use descriptive variable names — avoid single-letter names outside of loop indices.
- Add a brief comment above any non-obvious logic block.
- Keep cells focused: one logical step per cell where possible.
- Remove debug `print()` statements before submitting, unless they produce meaningful output for the reader.

---

## Submitting a Pull Request

1. **Commit your changes** with a clear message:
   ```bash
   git add .
   git commit -m "Add random forest comparison model"
   ```

2. **Push to your fork:**
   ```bash
   git push origin feature/your-feature-name
   ```

3. **Open a Pull Request** against the `main` branch of the original repository.

4. In your PR description, include:
   - A summary of what was changed and why
   - Any new dependencies introduced
   - Before/after output or metrics if relevant

---

## Reporting Issues

If you encounter a bug or unexpected behavior, please open an issue and include:

- A clear description of the problem
- The cell number(s) where the error occurs
- The full error message or traceback
- Your Python version and key package versions:
  ```bash
  python --version
  pip show pandas scikit-learn matplotlib openpyxl
  ```

For feature requests, describe the use case and the expected behavior you'd like to see.

---

## Questions

If you have questions about the project or are unsure where to start, feel free to open a discussion or issue — all skill levels are welcome.
