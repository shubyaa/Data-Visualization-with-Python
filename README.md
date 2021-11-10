# Data Visualization with _Pythton_

In this project, I have analyzed the [Airplane Crashes DataSet](https://www.kaggle.com/saurograndi/airplane-crashes-since-1908) which is available on [Kaggle](https://www.kaggle.com/).
With the help of Python libraries like [Plotly](https://plotly.com/), [Matplotlib](https://matplotlib.org/) and [Seaborn](https://seaborn.pydata.org/) the data is visualized using graphs, charts etc.

> _Hunting datasets ? , kaggle is the best platform to get one of those !!_

## This project undergoes into Three Main Stages-

1. Getting the data
2. Cleaning the data
3. Analyzing/Exploring the data

So Let's deeper into it !!

### **Getting the data**

We have a dataset of **Airplane Crashes** from **1908** to **2009**. The default format of the data is in **.csv**(comma-separated values). For this to import it in our project we will need [Pandas Dataframe](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.html).

```python
import pandas as pd
df = pd.read_csv('Airplane_Crashes_and_Fatalities_Since_1908.csv')
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
      <th>Date</th>
      <th>Time</th>
      <th>Location</th>
      <th>Operator</th>
      <th>Flight #</th>
      <th>Route</th>
      <th>Type</th>
      <th>Registration</th>
      <th>cn/In</th>
      <th>Aboard</th>
      <th>Fatalities</th>
      <th>Ground</th>
      <th>Summary</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>09/17/1908</td>
      <td>17:18</td>
      <td>Fort Myer, Virginia</td>
      <td>Military - U.S. Army</td>
      <td>NaN</td>
      <td>Demonstration</td>
      <td>Wright Flyer III</td>
      <td>NaN</td>
      <td>1</td>
      <td>2.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>During a demonstration flight, a U.S. Army fly...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>07/12/1912</td>
      <td>06:30</td>
      <td>AtlantiCity, New Jersey</td>
      <td>Military - U.S. Navy</td>
      <td>NaN</td>
      <td>Test flight</td>
      <td>Dirigible</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5.0</td>
      <td>5.0</td>
      <td>0.0</td>
      <td>First U.S. dirigible Akron exploded just offsh...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>08/06/1913</td>
      <td>NaN</td>
      <td>Victoria, British Columbia, Canada</td>
      <td>Private</td>
      <td>-</td>
      <td>NaN</td>
      <td>Curtiss seaplane</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>The first fatal airplane accident in Canada oc...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>09/09/1913</td>
      <td>18:30</td>
      <td>Over the North Sea</td>
      <td>Military - German Navy</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Zeppelin L-1 (airship)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20.0</td>
      <td>14.0</td>
      <td>0.0</td>
      <td>The airship flew into a thunderstorm and encou...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>10/17/1913</td>
      <td>10:30</td>
      <td>Near Johannisthal, Germany</td>
      <td>Military - German Navy</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>Zeppelin L-2 (airship)</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>30.0</td>
      <td>30.0</td>
      <td>0.0</td>
      <td>Hydrogen gas which was being vented was sucked...</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>5263</th>
      <td>05/20/2009</td>
      <td>06:30</td>
      <td>Near Madiun, Indonesia</td>
      <td>Military - Indonesian Air Force</td>
      <td>NaN</td>
      <td>Jakarta - Maduin</td>
      <td>Lockheed C-130 Hercules</td>
      <td>A-1325</td>
      <td>1982</td>
      <td>112.0</td>
      <td>98.0</td>
      <td>2.0</td>
      <td>While on approach, the military transport cras...</td>
    </tr>
    <tr>
      <th>5264</th>
      <td>05/26/2009</td>
      <td>NaN</td>
      <td>Near Isiro, DemocratiRepubliCongo</td>
      <td>Service Air</td>
      <td>NaN</td>
      <td>Goma - Isiro</td>
      <td>Antonov An-26</td>
      <td>9Q-CSA</td>
      <td>5005</td>
      <td>4.0</td>
      <td>4.0</td>
      <td>NaN</td>
      <td>The cargo plane crashed while on approach to I...</td>
    </tr>
    <tr>
      <th>5265</th>
      <td>06/01/2009</td>
      <td>00:15</td>
      <td>AtlantiOcean, 570 miles northeast of Natal, Br...</td>
      <td>Air France</td>
      <td>447</td>
      <td>Rio de Janeiro - Paris</td>
      <td>Airbus A330-203</td>
      <td>F-GZCP</td>
      <td>660</td>
      <td>228.0</td>
      <td>228.0</td>
      <td>0.0</td>
      <td>The Airbus went missing over the AtlantiOcean ...</td>
    </tr>
    <tr>
      <th>5266</th>
      <td>06/07/2009</td>
      <td>08:30</td>
      <td>Near Port Hope Simpson, Newfoundland, Canada</td>
      <td>Strait Air</td>
      <td>NaN</td>
      <td>Lourdes de BlanSablon - Port Hope Simpson</td>
      <td>Britten-Norman BN-2A-27 Islander</td>
      <td>C-FJJR</td>
      <td>424</td>
      <td>1.0</td>
      <td>1.0</td>
      <td>0.0</td>
      <td>The air ambulance crashed into hills while att...</td>
    </tr>
    <tr>
      <th>5267</th>
      <td>06/08/2009</td>
      <td>NaN</td>
      <td>State of Arunachal Pradesh, India</td>
      <td>Military - Indian Air Force</td>
      <td>NaN</td>
      <td>Mechuka for Jorhat</td>
      <td>Antonov An-32</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>13.0</td>
      <td>0.0</td>
      <td>The military transport went missing while en r...</td>
    </tr>
  </tbody>
</table>

<p>5268 rows × 13 columns</p>

</div>

### **Cleaning the Data**

As an observation, the data seems to be filled with errors and null values. This may cause in creating misleading data and degrades accuracy. Hence, cleaning of data is must. This is done by replacing null values and replacing unknown string values with empty strings.

After Cleaning the data lets check for null values if available.

```python
df.isnull().value_counts()
```

> _Note! Since we need only some columns for analysis, we have cleaned only those required columns to make ourselves more productive._

Also, after cleaning the data, we need to arrange our data as per our requirments. In this project, I have joined to columns **Date** & **Time** and formatted them with **Python datetime** format so that I can get only years from the entire date or day object.

Other opetions like getting the data into smaller fragments like **_groupby()_**, **_join()_** due to which our actual Dataset is not overwritten.

### **Analyzing the Data**

Finally, with all our settings or adjustments done, we can plot or graphs!

Here are some of the graphs:-

#### **Crash Accidents in a year**

![graph 1](https://github.com/shubyaa/Data-Visualization-with-Python/blob/main/images/graph_1.png)

#### **Barplot**

![graph 2](https://github.com/shubyaa/Data-Visualization-with-Python/blob/main/images/graph_2.png)

**This is the short video of the Results**

[![output](https://www.youtube.com/watch?v=Q9bsSQgBanc)
