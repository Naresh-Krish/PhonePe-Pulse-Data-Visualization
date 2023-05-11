# PhonePe-Pulse-Data-Visualization

# Required libraries to be imported
import pandas as pd
import os
import json
import sqlite3

# Cloning the data 
```!git clone https://github.com/PhonePe/pulse.git```

# Creating dataframes using Pandas
```Path1 ={'State':[], 'Year':[],'Quarter':[],'Transaction_type':[], 'Transaction_count':[], 'Transaction_amount':[]}

for i in Agg_state_list:
  p_i=path+i+"/"
  Agg_yr=os.listdir(p_i)    
  for j in Agg_yr:
    p_j=p_i+j+"/"
    Agg_yr_list=os.listdir(p_j)        
    for k in Agg_yr_list:
      p_k=p_j+k
      Data=open(p_k,'r')
      D=json.load(Data)
      for z in D['data']['transactionData']:
        Name=z['name']
        count=z['paymentInstruments'][0]['count']
        amount=z['paymentInstruments'][0]['amount']
        Path1['Transaction_type'].append(Name)
        Path1['Transaction_count'].append(count)
        Path1['Transaction_amount'].append(amount)
        Path1['State'].append(i)
        Path1['Year'].append(j)
        Path1['Quarter'].append(int(k.strip('.json')))
```
# Successfully created a dataframe

```
Agg_Transactions = pd.DataFrame(Path1)
Agg_Transactions
```
