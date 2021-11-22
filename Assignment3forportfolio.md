#### Importing data into a data frame that we can work with.


```
import pandas as pd

# This line makes pandas show you all of a DataFrame
pd.set_option('display.max_columns', None)
```

#### Reading in the data file that we want to work with

In this case, the data that we were working with was in the folder 's01' and was named 's01.txt'


```
df = pd.read_csv('s01/s01.txt')
```

#### Taking a look at our data using the pandas function head()


```
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id\tyear\tmonth\tday\thour\tminute\tgender\tage\thandedness\twait\tblock\ttrial\ttarget_location\ttarget\tflankers\trt\tresponse\terror\tpre_target_response\tITI_response\ttarget_on_error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>001\t2015\t05\t22\t11\t30\tm\t25\tr\t3.24\tpra...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>001\t2015\t05\t22\t11\t30\tm\t25\tr\t3.24\tpra...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>001\t2015\t05\t22\t11\t30\tm\t25\tr\t3.24\tpra...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>001\t2015\t05\t22\t11\t30\tm\t25\tr\t3.24\tpra...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>001\t2015\t05\t22\t11\t30\tm\t25\tr\t3.24\tpra...</td>
    </tr>
  </tbody>
</table>
</div>



Initially looking at our data, we can see that this is likely not a format that we want to work with. To make it easier to read and easier to perform operations on, we can specify that we want to separate the data in the data frame into columns based on the key '\t'.


```
df = pd.read_csv('s01/s01.txt', sep='\t')
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>year</th>
      <th>month</th>
      <th>day</th>
      <th>hour</th>
      <th>minute</th>
      <th>gender</th>
      <th>age</th>
      <th>handedness</th>
      <th>wait</th>
      <th>block</th>
      <th>trial</th>
      <th>target_location</th>
      <th>target</th>
      <th>flankers</th>
      <th>rt</th>
      <th>response</th>
      <th>error</th>
      <th>pre_target_response</th>
      <th>ITI_response</th>
      <th>target_on_error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>3.24</td>
      <td>practice</td>
      <td>1</td>
      <td>left</td>
      <td>black</td>
      <td>incongruent</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>False</td>
      <td>False</td>
      <td>0.023</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>3.24</td>
      <td>practice</td>
      <td>2</td>
      <td>right</td>
      <td>black</td>
      <td>incongruent</td>
      <td>0.550</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.023</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>3.24</td>
      <td>practice</td>
      <td>3</td>
      <td>up</td>
      <td>white</td>
      <td>incongruent</td>
      <td>0.565</td>
      <td>white</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>3.24</td>
      <td>practice</td>
      <td>4</td>
      <td>up</td>
      <td>black</td>
      <td>congruent</td>
      <td>0.453</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.024</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1</td>
      <td>2015</td>
      <td>5</td>
      <td>22</td>
      <td>11</td>
      <td>30</td>
      <td>m</td>
      <td>25</td>
      <td>r</td>
      <td>3.24</td>
      <td>practice</td>
      <td>5</td>
      <td>down</td>
      <td>black</td>
      <td>congruent</td>
      <td>0.442</td>
      <td>black</td>
      <td>True</td>
      <td>False</td>
      <td>False</td>
      <td>0.023</td>
    </tr>
  </tbody>
</table>
</div>




```

```
