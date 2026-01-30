# Car Price Prediction & Analysis 🚗⚡

> **A comprehensive Data Mining project analyzing factors affecting car prices for both electric and internal combustion engine vehicles using advanced statistical modeling.**

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Python](https://img.shields.io/badge/python-3.8%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

## ✨ Key Features

This project delves deep into automotive data to uncover pricing dynamics through:

- **Dual-Dataset Analysis**: Comparative study of Electric Vehicles (EVs) vs. Internal Combustion Engine (ICE) cars.
- **Robust Data Cleaning**: Automated handling of missing values, unit conversions (e.g., `sec` to float), and spelling corrections.
- **Exploratory Data Analysis (EDA)**: Visualizing correlations between features like `Horsepower`, `Range`, `Efficiency`, and `Price`.
- **Statistical Modeling**: Implementation of Linear Regression models to predict vehicle prices based on key performance metrics.
- **Market Insights**: Deriving actionable insights on how features like "Fast Charging" or "Top Speed" influence market value.

## 🛠️ Tech Stack

The project leverages a powerful Python-based data science stack:

| Category              | Libraries                                                                                                                                                          |
| :-------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Core**              | ![Python](https://img.shields.io/badge/-Python-3776AB?logo=python&logoColor=white)                                                                                 |
| **Data Manipulation** | ![Pandas](https://img.shields.io/badge/-Pandas-150458?logo=pandas&logoColor=white) ![NumPy](https://img.shields.io/badge/-NumPy-013243?logo=numpy&logoColor=white) |
| **Visualization**     | ![Matplotlib](https://img.shields.io/badge/-Matplotlib-yellow) ![Seaborn](https://img.shields.io/badge/-Seaborn-blue)                                              |
| **Modeling**          | ![Statsmodels](https://img.shields.io/badge/-Statsmodels-red)                                                                                                      |

## 📂 Project Structure

```bash
├── 📁 .git/                   # Version control
├── 📄 CarData.csv             # Dataset for standard (ICE) vehicles
├── 📄 ElectricCarData.csv     # Dataset for Electric Vehicles (EVs)
├── 📓 Rana_Selim_Part1.ipynb  # Part 1: Analysis & Modeling for EVs
├── 📓 Rana_Selim_Part2.ipynb  # Part 2: Analysis & Modeling for ICE Cars
└── 📄 README.md               # Project documentation
```

## 🚀 Getting Started

Follow these steps to set up the project locally for development and analysis.

### Prerequisites

- **Python 3.8+**
- **Jupyter Notebook** or **JupyterLab**
- **Pip** (Python Package Installer)

### Installation

1.  **Clone the repository**:

    ```bash
    git clone https://github.com/rana00selim/Data-Mining.git
    cd Data-Mining
    ```

2.  **Install dependencies**:
    Since there is no `requirements.txt`, you can install the core libraries directly:

    ```bash
    pip install pandas numpy matplotlib seaborn statsmodels notebook
    ```

3.  **Launch Jupyter Notebook**:
    ```bash
    jupyter notebook
    ```

## 💡 Usage Examples

Here are some snippets demonstrating the core logic extracted from the notebooks.

### 1. Data Cleaning (Unit Conversion)

Converting string columns like `Accel` (e.g., "4.6 sec") to usable floats.

```python
import pandas as pd

# Load EV Dataset
df = pd.read_csv('./ElectricCarData.csv')

# Clean Acceleration Data
Acceleration = []
for item in df['Accel']:
    # Remove ' sec' and convert to float
    Acceleration.append(float(item.replace(' sec','')))

df['Accel'] = Acceleration
print(df[['Brand', 'Accel']].head())
```

### 2. Correlation Analysis

Visualizing how features correlate with Price.

```python
import seaborn as sb
import matplotlib.pyplot as plt

# Generate Correlation Matrix
plt.figure(figsize=(10, 8))
sb.heatmap(df.corr(), annot=True, cmap='coolwarm')
plt.title("Feature Correlation Heatmap")
plt.show()
```

## 🤝 Contribution & Support

Contributions are welcome! If you find a bug or want to add a feature:

1.  Fork the Project.
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the Branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

For support, please open an issue in the repository.

---

<p align="center">
  <small>Developed by Rana Selim - COMP 4605.1 Data Mining Final Project</small>
</p>
