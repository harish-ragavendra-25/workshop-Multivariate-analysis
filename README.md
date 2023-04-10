# workshop-Multivariate-analysis
# AIM:
write a python code to visualize the given data using bivariant analysis.

# algorithm:

# step1: 
import the csv file using pandas package. 
# step2:
store the data as dataframe in a variable.
# step3:
display the information of data such as datatypes,value counts,skewness
# step4: 
display the data in the barplot,scatter plot and heatmap.

# CODE:

```
import pandas as pd
import seaborn as sns
from matplotlib import pyplot as plt
df=pd.read_excel('/content/FlightInformation.xlsx')
df
```
```
df.info()
df.dtypes
df['Airline'].value_counts()
df.describe()
```
```
plt.figure(figsize=(30,10))
sns.scatterplot(x=df['Airline'],y=df['Price'],hue=df['Source'])
```
```
prices=df.loc[:,["Airline","Price"]]
prices=prices.groupby(by=["Airline"]).sum().sort_values(by="Price")
plt.figure(figsize=(30,10))
sns.barplot(x=prices.index,y="Price",data=prices)
plt.xticks(rotation=90)
plt.xlabel=("Airline")
plt.ylabel=("Price")
plt.show()
```
```
df=pd.read_excel('/content/FlightInformation.xlsx')
sns.heatmap(df.corr())
```

# OUTPUT:

![Screenshot from 2023-04-05 14-30-31](https://user-images.githubusercontent.com/114852180/230034471-fdc9c087-284f-4a9e-835a-05c6b4c4c7b8.png)
![Screenshot from 2023-04-05 14-34-17](https://user-images.githubusercontent.com/114852180/230035075-23d58c0a-db16-49ce-8e58-455867af3c31.png)
![Screenshot from 2023-04-05 14-36-22](https://user-images.githubusercontent.com/114852180/230035197-0020e385-14ea-4de3-a086-3be83b5bf072.png)
![Screenshot from 2023-04-05 14-36-51](https://user-images.githubusercontent.com/114852180/230035320-dfbee322-875c-4b6e-bc06-e5475e3c6285.png)
![Screenshot from 2023-04-05 14-37-17](https://user-images.githubusercontent.com/114852180/230035432-9d93d5b6-3766-4db7-9cb3-845ab7138783.png)
![Screenshot from 2023-04-05 14-37-54](https://user-images.githubusercontent.com/114852180/230036374-5c9ddbd1-70d8-4804-a9a7-aab63aaaff8b.png)
![Screenshot from 2023-04-05 14-41-55](https://user-images.githubusercontent.com/114852180/230036614-0f08b639-4f88-419d-8e39-fd8cba0870b0.png)
![Screenshot from 2023-04-05 14-42-33](https://user-images.githubusercontent.com/114852180/230036749-f7bae8ed-a762-47e3-956e-d16b839004e2.png)

# RESULT:

Thus the experiment executed sucessfully.

