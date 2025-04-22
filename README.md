# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 15.04.2025
# NAME :SANJAY A
REG.NO: 212224040288

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Load the data
data = pd.read_csv("AirPassengers.csv")
# Create DataFrame
df = pd.DataFrame(data)

# Regular differencing
df['Regular Difference'] = df['#Passengers'].diff()

# Seasonal adjustment
result = seasonal_decompose(df['#Passengers'], model='additive', period=12)
df['Seasonal Adjustment'] = result.resid

# Log transformation
df['Log Transformation'] = np.log(df['#Passengers'])

# Plotting
plt.figure(figsize=(14, 10))

plt.subplot(4, 1, 1)
plt.plot(df['#Passengers'], label='Original')
plt.legend(loc='best')
plt.title('Original Data')

plt.subplot(4, 1, 2)
plt.plot(df['Regular Difference'], label='Regular Difference')
plt.legend(loc='best')
plt.title('Regular Differencing')

plt.subplot(4, 1, 3)
plt.plot(df['Seasonal Adjustment'], label='Seasonal Adjustment')
plt.legend(loc='best')
plt.title('Seasonal Adjustment')

plt.subplot(4, 1, 4)
plt.plot(df['Log Transformation'], label='Log Transformation')
plt.legend(loc='best')
plt.title('Log Transformation')

plt.tight_layout()
plt.show()


### OUTPUT:

![WhatsApp Image 2025-04-22 at 17 54 47_2d533545](https://github.com/user-attachments/assets/e4a21277-f1c0-45a6-918e-926eff0a91fb)


REGULAR DIFFERENCING:


![WhatsApp Image 2025-04-22 at 17 54 59_245cf442](https://github.com/user-attachments/assets/8ae4da7f-9e47-45e3-b011-86685593c95f)


SEASONAL ADJUSTMENT:

![WhatsApp Image 2025-04-22 at 17 55 15_20bfbc60](https://github.com/user-attachments/assets/7e43109b-9f7b-4d18-9281-bbd82dfe023a)


LOG TRANSFORMATION:


![WhatsApp Image 2025-04-22 at 17 55 29_447f60cb](https://github.com/user-attachments/assets/59f60aeb-d6a5-439c-9fda-8bcdd133d8e2)


### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
