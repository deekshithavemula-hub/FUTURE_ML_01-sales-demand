# FUTURE_ML_01-sales-demand
Task 1: Sales & Demand Forecasting
Objective
Predict future sales using historical sales data.
Python Code
Python
import pandas as pd
from sklearn.linear_model import LinearRegression
import matplotlib.pyplot as plt

# Sample Data
data = {
    'Month': [1, 2, 3, 4, 5, 6],
    'Sales': [100, 120, 140, 160, 180, 200]
}

df = pd.DataFrame(data)

X = df[['Month']]
y = df['Sales']

# Train Model
model = LinearRegression()
model.fit(X, y)

# Predict Future Sales
future_months = pd.DataFrame({'Month': [7, 8, 9, 10]})
predictions = model.predict(future_months)

print("Future Sales Forecast:")
for month, sale in zip(future_months['Month'], predictions):
    print(f"Month {month}: {sale:.2f}")

# Plot
plt.plot(df['Month'], df['Sales'], marker='o', label='Actual Sales')
plt.plot(future_months['Month'], predictions,
         marker='o', linestyle='--', label='Forecast')
plt.xlabel("Month")
plt.ylabel("Sales")
plt.legend()
plt.show()
Output
Plain text
Month 7: 220
Month 8: 240
Month 9: 260
Month 10: 280
