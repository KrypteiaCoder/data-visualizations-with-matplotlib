# data-visualizations-with-matplotlib
Images NF3 emissions

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
%matplotlib inline
df = pd.read_csv('/Users/manueltanguma/Downloads/UNdata_Export_20180605_141050855.csv')
pd.options.display.max_rows = 265
print (df)

plt.style.use('ggplot')

fig, ax = plt.subplots(figsize=(15,7))
df.groupby(['Year','Country or Area']).sum()['Value'].unstack().plot(ax=ax)
ax.set_xlabel('Year')
ax.set_ylabel('Value')

fig, ax = plt.subplots(figsize=(30,20))
plt.suptitle('')
df.boxplot(column=['Value'], by='Country or Area', ax=ax)
