# Problem Statement

Make an ARIMA model over shampoo sales data and check the MSE between predicted and actual value.

### Download data in .csv format from the following link:

https://datamarket.com/data/set/22r0/sales-of-shampoo-over-a-three-year-period#!ds=22r0&display=line

### Code to import packages and data:

    from pandas import read_csv
    from pandas import datetime
    from matplotlib import pyplot
    from statsmodels.tsa.arima_model import ARIMA
    from sklearn.metrics import mean_squared_error
    
    def parser(x):
        return datetime.strptime('190'+x, '%Y-%m')
        
    series = read_csv('shampoo-sales.csv', header=0, parse_dates=[0], index_col=0, squeeze=True, date_parser=parser)
