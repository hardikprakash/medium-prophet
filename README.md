# Prophet Time Series Forecasting

This project demonstrates how to use the Prophet library for time series forecasting. The dataset used in this project is the Electric Production dataset.

## Installation

To install the required dependencies, run the following command:

```bash
pip install prophet ipywidgets pandas matplotlib
```

## Usage

1. Clone the repository and navigate to the project directory.

2. Open the Jupyter notebook `1.ipynb` to see the step-by-step implementation.

3. The notebook includes the following steps:
   - Importing necessary libraries
   - Loading and preprocessing the dataset
   - Visualizing the data
   - Filtering data for specific date ranges
   - Building and fitting the Prophet model
   - Making future predictions
   - Plotting the forecast and its components

## Example

Here is a brief example of how to use the Prophet library for forecasting:

```python
import pandas as pd
from prophet import Prophet
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv('/path/to/Electric_Production.csv')
df['DATE'] = pd.to_datetime(df['DATE'])
df.rename(columns={'DATE': 'ds', 'IPG2211A2N': 'y'}, inplace=True)

# Initialize the model
model = Prophet()

# Fit the model
model.fit(df)

# Create future dates
future = model.make_future_dataframe(periods=730)

# Make predictions
forecast = model.predict(future)

# Plot the forecast
model.plot(forecast)
plt.show()
```