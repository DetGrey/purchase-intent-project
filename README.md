# Purchase Intent Project

A comparative study evaluating whether behavioral segmentation through clustering improves the accuracy of online purchase intent prediction using machine learning.

## Project Structure

- **prediction.ipynb** - Supervised learning: baseline models (Logistic Regression, Decision Tree, Random Forest) and hyperparameter tuning
- **clustering.ipynb** - Unsupervised learning: K-Means clustering and DBSCAN comparison, integration with tuned model
- **comparison.md** - Performance comparison between models with and without clustering
- **report** - LaTeX files for the final report
  - report.tex - Main report document
  - synopsis.tex - Project synopsis
  - refs.bib - Bibliography
  - notes.tex - Feedback notes

## Setup

### Requirements

- Python 3.13+ (see .python-version)
- uv package manager
- Dependencies managed via pyproject.toml

### Installation

1. Clone the repository
2. Install uv (if not already installed):
   ```bash
   pip install uv
   ```
3. Install dependencies:
   ```bash
   uv sync
   ```

### Dataset

The dataset might already be there as the file is only 1 mb large.

Download the **Online Shoppers Purchasing Intention Dataset** from the [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/468/online+shoppers+purchasing+intention+dataset) and place `online_shoppers_intention.csv` in the project root.

## Running the Analysis

Open and run the notebooks in order:

1. prediction.ipynb - trains baseline and tuned supervised models
2. clustering.ipynb - performs clustering and evaluates combined approach

Results are compared in comparison.md.