# weather-forcasting
In this particular project, Developed accurate weather forecasts by analyzing data and using mathematical models and physics to interpret collected information. Reviewed information from radar and satellite imagery, weather reporting agencies and air station observations to compile and analyze data for weather reports
: import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
[2]: !pip install plotly
Collecting plotly
Downloading plotly-5.15.0-py2.py3-none-any.whl (15.5 MB)
Collecting tenacity>=6.2.0
Downloading tenacity-8.2.2-py3-none-any.whl (24 kB)
Requirement already satisfied: packaging in c:\users\admin\anaconda3\lib\sitepackages (from plotly) (20.9)
Requirement already satisfied: pyparsing>=2.0.2 in
c:\users\admin\anaconda3\lib\site-packages (from packaging->plotly) (2.4.7)
Installing collected packages: tenacity, plotly
Successfully installed plotly-5.15.0 tenacity-8.2.2
[3]: import plotly.express as px
[4]: data=pd.read_csv(r"C:\Users\Admin\Downloads\ml project\DailyDelhiClimateTrain.
↪csv")
[5]: data.head
[5]: <bound method NDFrame.head of date meantemp humidity
wind_speed meanpressure
0 2013-01-01 10.000000 84.500000 0.000000 1015.666667
1 2013-01-02 7.400000 92.000000 2.980000 1017.800000
2 2013-01-03 7.166667 87.000000 4.633333 1018.666667
3 2013-01-04 8.666667 71.333333 1.233333 1017.166667
4 2013-01-05 6.000000 86.833333 3.700000 1016.500000
… … … … … …
1457 2016-12-28 17.217391 68.043478 3.547826 1015.565217
1458 2016-12-29 15.238095 87.857143 6.000000 1016.904762
1459 2016-12-30 14.095238 89.666667 6.266667 1017.904762
1460 2016-12-31 15.052632 87.000000 7.325000 1016.100000
1461 2017-01-01 10.000000 100.000000 0.000000 1016.000000
1
[1462 rows x 5 columns]>
[6]: data.head()
[6]: date meantemp humidity wind_speed meanpressure
0 2013-01-01 10.000000 84.500000 0.000000 1015.666667
1 2013-01-02 7.400000 92.000000 2.980000 1017.800000
2 2013-01-03 7.166667 87.000000 4.633333 1018.666667
3 2013-01-04 8.666667 71.333333 1.233333 1017.166667
4 2013-01-05 6.000000 86.833333 3.700000 1016.500000
[7]: data.describe()
[7]: meantemp humidity wind_speed meanpressure
count 1462.000000 1462.000000 1462.000000 1462.000000
mean 25.495521 60.771702 6.802209 1011.104548
std 7.348103 16.769652 4.561602 180.231668
min 6.000000 13.428571 0.000000 -3.041667
25% 18.857143 50.375000 3.475000 1001.580357
50% 27.714286 62.625000 6.221667 1008.563492
75% 31.305804 72.218750 9.238235 1014.944901
max 38.714286 100.000000 42.220000 7679.333333
[8]: data.info()
<class 'pandas.core.frame.DataFrame'>
RangeIndex: 1462 entries, 0 to 1461
Data columns (total 5 columns):
# Column Non-Null Count Dtype
--- ------ -------------- -----
0 date 1462 non-null object
1 meantemp 1462 non-null float64
2 humidity 1462 non-null float64
3 wind_speed 1462 non-null float64
4 meanpressure 1462 non-null float64
dtypes: float64(4), object(1)
memory usage: 51.5+ KB
[9]: data.isnull().sum()
[9]: date 0
meantemp 0
humidity 0
wind_speed 0
meanpressure 0
dtype: int64
