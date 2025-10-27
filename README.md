# Linear Regression Analysis: Vehicle Pricing Prediction

A comprehensive statistical analysis using linear regression modeling in R to investigate the relationship between vehicle characteristics and selling prices in the used car market. This project explores both technical specifications and market factors to identify key predictors of vehicle value.

## 🎯 Project Overview

This analysis examines how various characteristics of used vehicles affect their selling prices. Using a dataset of 3,314 used vehicle records, we developed and compared two linear regression models to understand the relative importance of technical features (engine power, mileage, fuel efficiency) versus market factors (transmission type, ownership history, seller type) in determining vehicle prices.

**Key Question:** What factors most strongly influence the selling price of a used vehicle?

## 📊 Dataset

The dataset contains 3,314 observations of used vehicles with the following variables:

**Technical Characteristics:**
- `selling_price` (numeric): Selling price in US dollars (dependent variable)
- `km_driven` (numeric): Total kilometers driven
- `mileage` (numeric): Fuel consumption in miles per gallon
- `engine` (numeric): Engine volume in cubic centimeters (CC)
- `max_power` (numeric): Maximum horsepower in brake horsepower (bhp)

**Market Factors:**
- `seller_type` (categorical): Individual or Dealer
- `transmission` (categorical): Manual or Automatic
- `owner` (categorical): Number of previous owners (First, Second, Third, Fourth & Above)
- `seats` (categorical): Number of seats in the vehicle

**Data Processing:**
- Original observations: 3,425
- Removed observations with missing values: 111
- Final complete observations: 3,314

## 🔬 Methodology

### Model 1: Technical Characteristics
A linear regression model using only technical specifications:
- Predictors: `km_driven`, `mileage`, `engine`, `max_power`, `engine:max_power`
- Interaction term captures the relationship between engine size and power output
- **Adjusted R²: 0.7891**

### Model 2: Comprehensive Model
An extended model incorporating both technical and market factors:
- All technical predictors from Model 1
- Additional market predictors: `seller_type`, `transmission`, `owner`, `seats`
- **Adjusted R²: 0.7885**

### Model Evaluation
- **Cross-Validation:** 10-fold cross-validation with 80/20 train-test split
- **Performance Metric:** Root Mean Squared Error (RMSE)
- **Result:** Model 2 achieved lower average RMSE, indicating better predictive accuracy despite slightly lower R²

## 📈 Key Findings

### Positive Price Predictors (increase value):
- ✅ **Higher fuel efficiency** (mileage in mpg)
- ✅ **Greater engine power** (max_power)
- ✅ **Optimal engine size-to-power ratio** (engine:max_power interaction)
- ✅ **Automatic transmission**
- ✅ **Dealer sellers**
- ✅ **Fewer previous owners**

### Negative Price Predictors (decrease value):
- ❌ **Higher kilometers driven**
- ❌ **Larger engine size** (without proportionate power increase)
- ❌ **Manual transmission**
- ❌ **Individual sellers**
- ❌ **Multiple previous owners**
- ❌ **Higher seat count**

## 🚀 Getting Started

### Prerequisites
- R (version 4.3.2 or higher)
- RStudio (recommended)
- Required R packages:
  ```r
  install.packages(c("caret", "knitr", "scales"))
  ```

### Running the Analysis

1. **Clone the repository:**
   ```bash
   git clone https://github.com/rmurage05/Linear-Regression-Analysis.git
   cd Linear-Regression-Analysis
   ```

2. **Open in RStudio:**
   - Open `vehicle_price_analysis.Rmd` in RStudio
   - Ensure `dataset3-3.csv` is in the same directory

3. **Install required packages** (if not already installed):
   ```r
   install.packages(c("caret", "knitr", "scales"))
   ```

4. **Knit the document:**
   - Click the "Knit" button in RStudio, or
   - Run: `rmarkdown::render("vehicle_price_analysis.Rmd")`

5. **View the output:**
   - A PDF report will be generated showing all analyses and visualizations

## 📁 Project Structure

```
Linear-Regression-Analysis/
├── README.md                      # Project documentation
├── vehicle_price_analysis.Rmd     # R Markdown source code
├── vehicle_price_analysis.pdf     # Compiled report with findings
└── dataset3-3.csv                 # Used vehicle dataset
```

## 📊 Visualizations

The analysis includes:
- **Distribution plots** for selling price and categorical variables
- **Residual plots** to validate model assumptions
- **QQ plots** to check normality of residuals
- **RMSE comparison plots** across cross-validation folds

## 🎓 Statistical Techniques Used

- **Linear Regression Modeling**
- **Interaction Terms** (engine × max_power)
- **Exploratory Data Analysis (EDA)**
- **K-Fold Cross-Validation** (k=10)
- **Root Mean Squared Error (RMSE)** evaluation
- **Hypothesis Testing** for coefficient significance
- **Residual Analysis** for model diagnostics

## 📝 Results Summary

| Model | Adj. R² | Avg. RMSE | Best For |
|-------|---------|-----------|----------|
| Model 1 (Technical Only) | 0.7891 | Higher | Understanding technical impact |
| Model 2 (Comprehensive) | 0.7885 | **Lower** | **Prediction accuracy** |

**Conclusion:** Model 2, which incorporates both technical specifications and market factors, provides the best predictive performance. This suggests that vehicle pricing in the used car market is influenced by both the physical characteristics of the vehicle and market perception factors.

## 💡 Key Insights for Used Car Market

1. **Technical specifications matter most** - Engine power and fuel efficiency are strong positive predictors
2. **Usage history impacts value** - Higher mileage and multiple owners significantly reduce price
3. **Transmission type is significant** - Automatic transmissions command premium prices
4. **Market perception matters** - Dealer sales and first-owner vehicles fetch higher prices
5. **Holistic evaluation necessary** - Best predictions require considering both technical and market factors

## 🔮 Future Work

Potential extensions of this analysis:
- Include additional variables (brand, model, year, location)
- Explore non-linear relationships and polynomial terms
- Test advanced models (Random Forest, Gradient Boosting)
- Analyze regional price variations
- Incorporate time-series analysis for price trends

## 📄 Report

The full analysis report is available in `vehicle_price_analysis.pdf`, which includes:
- Detailed methodology
- Complete statistical results
- All visualizations and tables
- Comprehensive interpretation of findings

## 🛠️ Technologies Used

- **R** (4.3.2) - Statistical computing and graphics
- **RStudio** - Integrated development environment
- **R Markdown** - Dynamic document generation
- **caret** - Machine learning and cross-validation
- **knitr** - Report generation
- **scales** - Data visualization formatting

## 👤 Author

**Ryan K. Murage**
- GitHub: [@rmurage05](https://github.com/rmurage05)
- LinkedIn: [ryan-murage](https://www.linkedin.com/in/ryan-murage)

## 📜 License

This project is open source and available for educational purposes.

## 🙏 Acknowledgments

- Dataset sourced from the used auto industry
- Statistical methodologies based on standard linear regression practices
- Analysis conducted as part of data science coursework at UMass Amherst

---

**Note:** This analysis is based on a specific dataset and time period. Results may vary with different data or market conditions. The findings are intended for educational and informational purposes.