# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Reg no: 212224230001

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt


data = pd.read_csv('Toyota.csv')


print(data.columns)


series = data['Price']


series_filled = series.fillna(method='ffill')


plt.figure(figsize=(10,4))
plt.plot(series_filled, label='Original Price')
plt.title('Original Price Series')
plt.xlabel('Index')
plt.ylabel('Price')
plt.legend()
plt.show()


diff_series = series_filled.diff().dropna()
plt.figure(figsize=(10,4))
plt.plot(diff_series, label='Differenced Price')
plt.title('After Regular Differencing')
plt.xlabel('Index')
plt.ylabel('Differenced Price')
plt.legend()
plt.show()


log_series = np.log(series_filled + 1)
plt.figure(figsize=(10,4))
plt.plot(log_series, label='Log-Transformed Price')
plt.title('Log-Transformed Series')
plt.xlabel('Index')
plt.ylabel('Log(Price+1)')
plt.legend()
plt.show()


seasonal_diff = series.diff(12).dropna()

plt.figure(figsize=(10,4))
plt.plot(seasonal_diff, label='Seasonally Differenced (lag=12)')
plt.title('Seasonally Differenced Price Series (Period=12)')
plt.legend()
plt.show()

```

### OUTPUT:


REGULAR DIFFERENCING:
<img width="1091" height="487" alt="image" src="https://github.com/user-attachments/assets/1a3b1b9e-f071-44d7-b74b-ef26077f9058" />


SEASONAL ADJUSTMENT:
<img width="1067" height="474" alt="image" src="https://github.com/user-attachments/assets/9b7d1a0d-1be2-4af4-bc1a-86bf60696610" />


LOG TRANSFORMATION:
<img width="1077" height="481" alt="image" src="https://github.com/user-attachments/assets/f49672ee-9f1d-4c49-aff0-6c27db071846" />



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
