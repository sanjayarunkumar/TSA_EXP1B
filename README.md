# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
from matplotlib import pyplot as plt
import pandas as pd
df=pd.read_csv("/content/AirPassengers.csv")
# df=pd.read_csv("/content/test.csv",parse_dates=["date"],index_col="date")
df.head()
df['Month']=pd.to_datetime(df['Month'])
df.dtypes
df.set_index('Month',inplace=True)
df_resampled = df['#Passengers'].resample('D').interpolate()
df_resampled.plot(kind='line',label='Total Sales', color='black')
plt.title('Time Series Plot of Number of passengers ecah day')
plt.xlabel('Day')
plt.ylabel('Number of passengers')
plt.legend()
plt.grid(True)
plt.show()


### OUTPUT:
![ea526e06-f004-4e5f-8b70-5fa93a0b2abc](https://github.com/user-attachments/assets/8d3110c1-e505-43e8-9848-f1cd2e8ca34b)


REGULAR DIFFERENCING:


SEASONAL ADJUSTMENT:


LOG TRANSFORMATION:



### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
