# UEFA Champions League Data Analysis

A comprehensive statistical analysis of UEFA Champions League dataset examining player performance, goal-scoring patterns, and team statistics using univariate, bivariate, and multivariate analytical techniques.

## Table of Contents
- [Problem Statement](#problem-statement)
- [Dataset Description](#dataset-description)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Installation and Usage](#installation-and-usage)
- [Results and Insights](#results-and-insights)

## Problem Statement

The objective of this project is to conduct a thorough statistical analysis of UEFA Champions League data to:

1. **Understand player performance distributions** - Analyze individual player statistics including goals, assists, and playing time
2. **Identify relationships between variables** - Examine correlations between different performance metrics
3. **Discover underlying patterns** - Use dimensionality reduction techniques to uncover hidden structures in the data
4. **Provide actionable insights** - Generate findings that can inform coaching decisions and tactical strategies

## Dataset Description

The analysis uses four CSV files containing UCL player and team statistics:

- **defending.csv** - Defensive statistics and metrics
- **disciplinary.csv** - Yellow/red cards and disciplinary records
- **distribution.csv** - Pass distribution and ball movement data
- **goalkeeping.csv** - Goalkeeper-specific statistics
- **attacking.csv** - Offensive statistics (loaded but not analyzed in current notebook)
- **attempts.csv** - Shot attempts and accuracy data
- **goals.csv** - Goal-scoring details including foot used and location
- **key_stats.csv** - Consolidated player statistics including goals, assists, minutes played, and positions

### Key Variables Analyzed

- Player positions
- Goals scored
- Assists provided
- Minutes played
- Shot attempts (total and on-target)
- Goal-scoring methods (right foot, left foot, inside area, outside area, penalties)

## Methodology

### 1. Univariate Analysis

Individual variable analysis to understand distributions and characteristics:

#### Statistical Measures Calculated
- **Centrality**: Mean, median, mode
- **Dispersion**: Standard deviation, variance, range, min, max
- **Quantiles**: 25th percentile, 75th percentile, interquartile range (IQR)
- **Shape**: Skewness, kurtosis
- **Inequality**: Gini index, Lorenz curve

#### Variables Analyzed
- Player positions (value counts distribution)
- Goals scored (players with ≥1 goal)
- Assists provided (players with ≥1 assist)
- Minutes played (players with ≥50 minutes)

### 2. Bivariate Analysis

Examining relationships between pairs of variables:

#### Analyses Performed
- **Contingency tables** - Cross-tabulation of categorical/discrete variables
- **Marginal distributions** - Proportions of each variable independently
- **Correlation analysis** - Pearson correlation coefficient
- **Linear regression** - Modeling relationships between variables
- **Hypothesis testing**:
  - T-test for comparing means
  - ANOVA for variance analysis
  - Chi-square test for independence

#### Variable Pairs Examined
1. Right-foot goals vs Left-foot goals
2. Total attempts vs On-target attempts

### 3. Multivariate Analysis

Principal Component Analysis (PCA) for dimensionality reduction:

#### PCA Process
1. **Data preprocessing** - Centering and scaling (z-score normalization)
2. **Matrix computation** - Covariance and correlation matrices
3. **Eigenvalue decomposition** - Extract principal components
4. **Component selection** - Using multiple criteria:
   - Scree plot visualization
   - Explained variance threshold (95%)
   - Kaiser criterion (eigenvalues > 1)
5. **Transformation** - Project data onto principal component space
6. **Interpretation** - Analyze variable contributions and correlations

#### Variables in PCA
- Right-foot goals
- Left-foot goals
- Goals from inside area
- Goals from outside areas
- Penalty goals

## Key Findings

### Univariate Insights

#### Player Positions
- Distribution shows concentration in specific position types
- Moderate variance in position frequency
- Gini index indicates distribution inequality

#### Goals Distribution
- Positive skewness indicates most players score fewer goals
- High kurtosis suggests presence of outlier scorers
- Clear distinction between regular scorers and elite performers

#### Assists Distribution
- Similar pattern to goals with right-skewed distribution
- Lower mean than goals, indicating assists are less common
- High variance among players with assists

#### Minutes Played
- Strong variation in playing time (filtered for ≥50 minutes)
- Distribution reflects squad rotation and player importance
- Correlation with performance metrics expected

### Bivariate Insights

#### Goal-Scoring Methods (Right vs Left Foot)
- Correlation coefficient reveals foot preference patterns
- Contingency analysis shows dominant foot usage
- Chi-square test indicates statistical significance of foot preference
- Linear regression models predictability of foot choice

#### Shot Accuracy (Total Attempts vs On-Target)
- Strong positive correlation expected between attempts and accuracy
- Linear regression quantifies conversion efficiency
- ANOVA reveals variance in shooting accuracy
- Visual analysis confirms relationship patterns

### Multivariate Insights (PCA)

#### Principal Components
- **PC1 (First Component)**: Captures maximum variance, likely representing overall goal-scoring ability
- **PC2 (Second Component)**: Distinguishes between different goal-scoring styles
- Components explain 95% of total variance with fewer dimensions

#### Variable Contributions
- Scree plot identifies optimal number of components
- Kaiser criterion validates component retention
- Variables show different loadings on principal components
- Penalty goals may have unique contribution pattern

#### Pattern Discovery
- Natural clustering of similar scoring profiles
- Identification of player archetypes based on goal-scoring patterns
- Dimensionality reduction maintains essential information

## Technologies Used

- **Python 3.x** - Primary programming language
- **pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization
- **scikit-learn** - Machine learning (PCA implementation)
- **SciPy** - Statistical tests and methods

## Project Structure

```
Data-Analysis-for-the-UCL-Data/
│
├── data/
│   ├── defending.csv
│   ├── disciplinary.csv
│   ├── distribution.csv
│   ├── goalkeeping.csv
│   ├── attacking.csv
│   ├── attempts.csv
│   ├── goals.csv
│   └── key_stats.csv
│
├── Project.ipynb          # Main analysis notebook
├── Report.pdf             # Detailed findings report
└── README.md              # Project documentation
```

## Installation and Usage

### Prerequisites
```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

### Running the Analysis
1. Clone or download the repository
2. Ensure all CSV files are in the `data/` directory
3. Open `Project.ipynb` in Jupyter Notebook or JupyterLab
4. Run cells sequentially to reproduce the analysis

### Data Path Configuration
Update the `kaggle_path` variable if your data is in a different location:
```python
kaggle_path = 'data/'  # Adjust path as needed
```

## Results and Insights

### Statistical Significance
- Multiple hypothesis tests confirm statistical significance of observed relationships
- P-values indicate confidence in findings
- Effect sizes quantified through correlation coefficients

### Practical Applications
1. **Player Scouting**: Identify undervalued players based on statistical profiles
2. **Tactical Planning**: Understand goal-scoring patterns to develop strategies
3. **Performance Evaluation**: Benchmark players against distribution statistics
4. **Squad Management**: Optimize playing time based on performance metrics

### Limitations
- Analysis limited to available features in dataset
- Temporal aspects not considered (season progression)
- Contextual factors (opponent strength, match importance) not included
- Sample size varies across different subsets (filtered data)

## Future Work

- **Time series analysis** - Examine performance trends over seasons
- **Clustering analysis** - Group players by similar characteristics
- **Predictive modeling** - Forecast future performance
- **Network analysis** - Study passing networks and team dynamics
- **Advanced visualizations** - Interactive dashboards for exploration
- **Feature engineering** - Create composite metrics for holistic evaluation

## Author

Data analysis project for UEFA Champions League statistics exploration.

## License

This project is intended for educational and analytical purposes.

---

*For detailed statistical outputs and visualizations, please refer to the Jupyter notebook and accompanying report.*
