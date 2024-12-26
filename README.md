
# Regression Analysis with R

This project demonstrates regression analysis using R to explore the relationship between advertising budgets and sales. It includes steps to calculate the regression line, make predictions, and evaluate the model using Mean Squared Error (MSE). The outputs also include graphical visualizations.

## Overview

The analysis includes:
1. Calculating the regression line equation: \(y = mx + b\)
2. Calculating residuals and Mean Squared Error (MSE)
3. Visualizing the regression line and residuals

## R Code

Below is the R code used for the analysis:

```R
# Input data: Advertising budget and sales
advertising <- c(10, 20, 30, 40, 50)
sales <- c(50, 65, 80, 95, 110)

# Calculate slope (m) and intercept (b)
n <- length(advertising)
m <- (n * sum(advertising * sales) - sum(advertising) * sum(sales)) / (n * sum(advertising^2) - (sum(advertising))^2)
b <- (sum(sales) - m * sum(advertising)) / n

# Predicted sales
predicted_sales <- m * advertising + b

# Calculate residuals
residuals <- sales - predicted_sales

# Mean Squared Error (MSE)
mse <- mean(residuals^2)

# Print regression equation and MSE
cat("Regression Equation: y =", round(m, 2), "x +", round(b, 2), "\n")
cat("Mean Squared Error (MSE):", round(mse, 2), "\n")

# Plot: Actual vs Predicted Sales
plot(advertising, sales, col = "blue", pch = 16, xlab = "Advertising Budget", ylab = "Sales",
     main = "Advertising Budget vs Sales")
abline(a = b, b = m, col = "red", lwd = 2)
legend("topleft", legend = c("Actual Sales", "Regression Line"), col = c("blue", "red"), pch = c(16, NA), lty = c(NA, 1))

# Plot: Residuals
plot(advertising, residuals, col = "purple", pch = 16, xlab = "Advertising Budget", ylab = "Residuals",
     main = "Residual Plot")
abline(h = 0, col = "red", lty = 2)
legend("bottomleft", legend = "Residuals", col = "purple", pch = 16)
```

## Outputs

### 1. Regression Equation and MSE
The script prints the regression equation and Mean Squared Error (MSE) in the console.

### 2. Graphs
- **Regression Line**: A scatter plot showing actual sales data and the regression line.
- **Residual Plot**: A plot showing residuals for each data point to evaluate model performance.

## How to Use

1. Copy the R code into your R console or RStudio.
2. Run the script.
3. Analyze the printed results and generated plots.

## Insights

- The regression equation helps in predicting sales based on advertising budgets.
- The MSE indicates how well the model fits the data.
- The residual plot evaluates the distribution of errors.

## Contact
For any queries or feedback, feel free to contact TannuWorks at agapaitanveermou@gmail.com.
