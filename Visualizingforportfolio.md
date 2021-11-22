### Visualizing data using the seaborn and matplotlib packages

Import the seaborn package


```python
import seaborn as sns
import matplotlib.pyplot as plt
sns.set_style('white')
```

We can use the displot() function and arguments from the seaborn package to display plots in a visually appealing way when there are more than one variable to show. Here I use the flanker data and the reaction time in milliseconds to show the difference between the congruent and incongruent flankers. This data had not been cleaned for outliers and showcases a skewed distribution.


```python
figure1 = sns.displot(data = df, x = 'rt_ms', hue = 'flankers')
plt.show()
```




    
![png](2021-11-21-223509_files/2021-11-21-223509_4_0.png)
    



We can also visualize data in other interesting ways like a violin plot:


```python
sns.catplot(kind = 'violin', data = df, x = 'flankers', y = 'rt_ms')
plt.show()
```




    
![png](2021-11-21-223509_files/2021-11-21-223509_6_0.png)
    


