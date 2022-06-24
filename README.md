# Air-Pollution-Prediction-using-k-NN

### Description:
This Python-based project predicted concentration values of NO, NO2, and NOX at Barking and Dagenham - Rush Green using k-NN variations - simple k-NN, inverse distance weighted k-NN, [1.0/(distance + 0.001)] weighted k-NN, Pearson correlation coefficient weighted k-NN, and information gain weighted k-NN. Apart from the Euclidean distance formula, two different distance formulae were explored.

#### Details:
* Dataset was collected from - [https://www.londonair.org.uk/LondonAir/Default.aspx](https://www.londonair.org.uk/LondonAir/Default.aspx)
* Location referred - Barking and Dagenham - Rush Green
* Duration observed - January 2014 to December 2018
* Time Interval - 15 minutes interval daily
* Pollutants taken - NO, NO<sub>2</sub>, NOX, SO<sub>2</sub>, BP, RAIN, RHUM, WDIR, SOLR, TMP, WSPD

#### Project Structure - 
`Preprocessing.ipynb` does the necessary data collection and merging, cleaning and preprocessing of the data. `Air Pollution Prediction using Attribute Weighted k-NN Methodology.pdf` gives the detailed working. With the preprocessed data `preprocessedData.csv`, we now dive into using it into variations of k-NN.

Filename follow the syntax `[number][attribute].[type]`. NO, NO<sub>2</sub> and NOX comes under `attribute` field. `type` field can be either ipnyb, jupyter notebook containing the code or csv, comma separated file containing the data. `number` field with the following numbers have:
- 1        - uniformly weighted k-NN 
- 2.1      - distance weighted k-NN with weights = *1/distance*
- 2.2      - weighted k-NN with weights = *1.0 /(distance + 0.001)*
- 3.1.1    - weighted k-NN with weights = correlation coefficient *r<sub>x<sub>p</sub>,y</sub>*, and distance = *sqrt(sum(abs(w<sub>p</sub>(u<sub>ip</sub> - v<sub>jp</sub>))<sup>2</sup>))*
- 3.1.2    - weighted k-NN with weights = *r<sub>x<sub>p</sub>,y</sub>*, and distance = *sqrt(sum(w<sub>p</sub>u<sub>ip</sub> - w<sub>p</sub>v<sub>jp</sub>)<sup>2</sup>)*
- 3.2.1    - weighted k-NN with weights = *|r<sub>x<sub>p</sub>,y</sub>|/(1 - |r<sub>x<sub>p</sub>,y</sub>|)*, and distance = *sqrt(sum(abs(w<sub>p</sub>(u<sub>ip</sub> - v<sub>jp</sub>))<sup>2</sup>))*
- 3.2.2    - weighted k-NN with weights = *|r<sub>x<sub>p</sub>,y</sub>|/(1 - |r<sub>x<sub>p</sub>,y</sub>|)*, and distance = *sqrt(sum(w<sub>p</sub>u<sub>ip</sub> - w<sub>p</sub>v<sub>jp</sub>)<sup>2</sup>)*
- 4.1.1    - weighted k-NN with weights = information gain, and target column is median substituted, and distance = *sqrt(sum(abs(w<sub>p</sub>(u<sub>ip</sub> - v<sub>jp</sub>))<sup>2</sup>))* 
- 4.1.2    - weighted k-NN with weights = information gain, and target column is not median substituted, and distance = *sqrt(sum(abs(w<sub>p</sub>(u<sub>ip</sub> - v<sub>jp</sub>))<sup>2</sup>))*
- 4.2.1    - weighted k-NN with weights = information gain, and target column is median substituted, and distance = *sqrt(sum(w<sub>p</sub>u<sub>ip</sub> - w<sub>p</sub>v<sub>jp</sub>)<sup>2</sup>)*
- 4.2.2    - weighted k-NN with weights = information gain, and target column is not median substituted, and distance = *sqrt(sum(w<sub>p</sub>u<sub>ip</sub> - w<sub>p</sub>v<sub>jp</sub>)<sup>2</sup>)*

`2.2(NO).csv` is the dataframe created to predicted values with the actual values. While `2.2NO.csv` contains time when the model completed predicting in each iteration.

`NO metrics`, `NO2 metrics`, and `NOX metrics` summarizes all models in terms of Time, Root Mean Square Error (RMSE), Mean Square Error (MSE), R-Square Error (R-squared), and Mean Absolute Error (MAE). 
