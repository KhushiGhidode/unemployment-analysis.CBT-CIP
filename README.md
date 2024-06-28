# unemployment-analysis.CBT-CIP
## Importing necessary libraries
import numpy as np
import pandas as pd
import plotly.graph_objs as go
%pip install nbformat>=4.2.0
%pip install plotly
import plotly.express as px
import matplotlib.pyplot as plt

#Reading CSV files 
df=pd.read_csv("kunemployment_Rate_upto_11_2020.csv")

# Displaying basic information about the dataframe
print(df.head())
print(df.tail())
print(df.shape)  # Returns tuple of shape (Rows, Columns) of dataframe
print(df.info())  # Prints info about dataframe
print(df.describe())  # Prints numerical description of the data in dataframe

## Importing necessary libraries
%pip install plotly

import plotly.express as px
import matplotlib.pyplot as plt

# Plotting using Plotly Express
fg = px.bar(df, x='Region', y='Estimated Unemployment Rate (%)', color='Region',
            title='Unemployment Rate (State-Wise) by Bar Graph', template='plotly')
fg.update_layout(xaxis={'categoryorder': 'total descending'})
fg.show()

fg = px.box(df, x='Region', y='Estimated Unemployment Rate (%)', color='Region',
            title='Unemployment Rate (State-Wise) by Box Graph', template='plotly')
fg.update_layout(xaxis={'categoryorder': 'total descending'})
fg.show()

fg = px.scatter(df, x='Region', y='Estimated Unemployment Rate (%)', color='Region',
               title='Unemployment Rate (State-Wise) by Scatter Graph', template='plotly')
fg.update_layout(xaxis={'categoryorder': 'total descending'})
fg.show()

fg = px.histogram(df, x='Region', y='Estimated Unemployment Rate (%)', color='Region',
                 title='Unemployment Rate (State-Wise) by Histogram', template='plotly')
fg.update_layout(xaxis={'categoryorder': 'total descending'})
fg.show()
