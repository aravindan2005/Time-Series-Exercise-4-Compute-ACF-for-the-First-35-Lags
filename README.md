# Time Series Exercise 4: Compute ACF for the First 35 Lags

## Name: Aravindan T

## Roll No: 2305001003

## Department: CSE

## AIM

To compute and plot the AutoCorrelation Function (ACF) of a time-series dataset for the first 35 lags and use the ACF pattern to identify a suitable time-series model.

## PROGRAM

### Python Code

```python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.stattools import acf
from statsmodels.graphics.tsaplots import plot_acf

data = [
    50, 55, 60, 58, 62, 70, 75, 72, 68, 60, 52, 58,
    62, 68, 74, 71, 78, 85, 90, 88, 82, 75, 65, 72,
    76, 82, 88, 85, 92, 100, 108, 105, 98, 90, 80, 88,
    92, 98, 105, 102, 110, 120
]

series = pd.Series(data)

plt.figure(figsize=(10, 4))
plt.plot(series, marker='o')
plt.title("Monthly Website Traffic")
plt.xlabel("Time (Months)")
plt.ylabel("Visitors (in thousands)")
plt.show()

acf_values = acf(series, nlags=35)

print("ACF Values:")
for lag, value in enumerate(acf_values):
    print("Lag", lag, ":", round(value, 4))

plot_acf(series, lags=35)
plt.title("ACF for First 35 Lags - Website Traffic")
plt.xlabel("Lag")
plt.ylabel("Autocorrelation")
plt.show()
```

## OUTPUT
<img width="940" height="385" alt="image" src="https://github.com/user-attachments/assets/1a75a2a4-d024-41ed-a303-b9b444f33e72" />
<img width="960" height="928" alt="image" src="https://github.com/user-attachments/assets/740fe9fa-beab-4c92-b37d-8062ccb6f401" />

## RESULT

The AutoCorrelation Function (ACF) was successfully computed and plotted for the first 35 lags. The ACF pattern was used to study the correlation between observations and help identify a suitable time-series model.
