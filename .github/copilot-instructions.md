# AI Coding Agent Instructions for Descriptive Statistics Project

## Project Overview
This is a Python-based learning project for descriptive statistics exercises. Students analyze movie title lengths from an IMDb dataset using pandas, numpy, matplotlib, and scipy in Jupyter notebooks.

## Key Architecture
- **Notebooks**: Main work in `notebook/problems.ipynb` (English) and `notebook/problems.es.ipynb` (Spanish)
- **Data**: IMDb dataset at `assets/imdb_1000.csv` with columns: star_rating, title, content_rating, genre, duration, actors_list
- **Solutions**: Reference implementations in `notebook/solutions.ipynb` and `notebook/solutions.es.ipynb`
- **Environment**: Python 3.11 devcontainer with pre-installed dependencies from `requirements.txt`

## Critical Workflows
- **Setup**: Open in Codespace, select Python 3.11 kernel in notebook
- **Development**: Execute cells sequentially, use `df["title"].str.len()` for title lengths
- **Validation**: Run `learnpack audit` locally or via GitHub Actions for automated grading
- **Delivery**: Commit changes, push to repo, submit link to 4Geeks.com

## Code Conventions
- **Statistics Calculations**: Use pandas methods for sample statistics (default ddof=1 for var/std)
- **Data Manipulation**: Create new columns with `df["new_col"] = df["existing"].str.len()` for string lengths
- **Visualization**: Use `plt.hist()` with `bins=20, density=True, alpha=0.6, color='g'` and `df['title_length'].plot(kind='kde')` or `sns.histplot()` with `kde=True`
- **Imports**: Standard pattern:
  ```python
  import pandas as pd
  import numpy as np
  import matplotlib.pyplot as plt
  import seaborn as sns
  from scipy.stats import skew, kurtosis, mode
  ```
- **Mode Calculation**: `df["column"].mode().item()` for single mode value
- **Range Calculation**: `df["column"].max() - df["column"].min()`

## Dependencies & Environment
- Core libraries: pandas, numpy, matplotlib, scipy, seaborn
- Environment: Managed via .devcontainer/devcontainer.json (Python 3.11)
- Extensions: Jupyter, Python (pre-installed)

## Common Patterns
- Load data: `df = pd.read_csv("../assets/imdb_1000.csv")`
- Title analysis: Focus on `title_length` column derived from `df['title'].str.len()`
- Output: Print results with f-strings, e.g., `print(f"Mean: {mean:.2f}")`
- Avoid modifying original dataset; create derived columns for analysis
- Use pandas for skew and kurtosis: `df["title_length"].skew()`, `df["title_length"].kurt()`</content>
<parameter name="filePath">/workspaces/CristinaChico23_Desciptive-statistics/.github/copilot-instructions.md