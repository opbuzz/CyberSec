

## Tuples

```python
# if you have two tuples in variables
first_coord  = (0, 1)
second_coord = (2, 3)


# you can unpack them with commas
first_x, first_y   = first_coord
second_x, second_y = second_coord
```

## Lists
### Sum all values in a list that are equal to x
```python
total  =  sum([1  for  n  in  list  if  n  ==  foo])
```


## NumPy


 ```python
import numpy as np
for i in fdfd:
```

#### Creating an Array from a CSV
```python
csv_array = np.genfromtxt('sample.csv',delimiter=',')
```
> NumPy Arrays are generally more efficient then lists
#### Select a range using array

```python
arr = np.array[1,2,3]
print(arr[1:3])
>>> 1,2

# selects the first column
>>> a[:,0]
array([32, 12,  2])

# selects the second row
>>> a[1,:]
array([12, 10,  5, 23,  1])

# selects the first three elements of the first row
>>> a[0,0:3]
array([32, 15,  6])
```
#### Logical Operations with Arrays

```python
>>> a = np.array([10, 2, 2, 4, 5, 3, 9, 8, 9, 7])
>>> a > 5
array([True, False, False, False, False, False, True, True, True, True], dtype=bool)

>>> a[a > 5]
array([10, 9, 8, 9, 7])

# using logical operations &,|

>>> a[(a > 5) | (a < 2)]
array([10, 9, 8, 9, 7])
```

### NumPy and Mean
```python
np.mean (axis = num)  #Defulat is 0 by rows, 1 by colunms

>>>  np.mean(survey_array  >  8)  0.2
```
#### Calculate the percentage of a given dataset
```python
percentage = np.mean(dataset > x)
```
#### Calculate the probability of a given number in a dataset
```python
percentage = np.mean(dataset == num)
```

### Sorting and Outliers
```python

```

###  Percentiles
```python
np.percentile()	
>>>  d  =  np.array([1, 2, 3, 4, 4, 4, 6, 6, 7, 8,  8])
>>>  np.percentile(d,  40)  
> 4.00
```
### STD

```python
np.std()	
>>>>  nums  =  np.array([65,  36,  52,  91,  63,  79])
>>>>  np.std(nums)  17.716909687891082
```

### Random
It takes the following arguments:

-   **N**: The number of samples or trials
-   **P**: The probability of success
-   **size**: The number of experiments
```python
# Let's generate 10,000 "experiments"  # N = 10 shots  
# P = 0.30 (30% he'll get a free throw)  
a  =  np.random.binomial(10,  0.30,  size=10000)
``` 
#### To generate random numbers from a normal distribution
```python
np.random.normal(loc=desired_mean,scale=desired_std,size=num_samples)
```
## Matplotlib

### Histograms

```python
from  matplotlib  import  pyplot  as  plt  
# This plots a histogram  
plt.hist(data) # bins and range are set auto if not defined 
plt.hist(data, bins =5, range(2,20)) 
# This displays the histogram  
plt.show()
```
## Math rules

helpful rules for normal distributions:

-   **68%**  of our samples will fall between +/- 1 standard deviation of the mean
-   **95%**  of our samples will fall between +/- 2 standard deviations of the mean
-   **99.7%**  of our samples will fall between +/- 3 standard deviations of the mean

### Pandas
#### Uses DataFrames which are like spreadsheets

```python
import panda as panda
```
##### Using dictionary 
Each key is a column name and each value is a list of column values. The columns must all be the same length or you will get an error
```python
 df1  =  pd.DataFrame({'string':['xxx',  'yyy'],
'num':[1,  2]})
```
##### Using Lists
 ```python
 df1 = pd.DataFrame(['xxx,1].['yyyy',2], columns = ['string','num'
 ```
 ### Read/write CSV
 ```python
pd.read_csv('my-csv-file.csv')
df.to_csv('new-csv-file.csv')
 ```
 ### Inspect DataFrame
 ```python
  # first 5 rows Default
  df.head()
  # Some stat
  df.info()
 ```
 ### Selecting columns
#### Select by name
 ```python
select_one_cpl  = df['col1']
select_mul_col = df[ ['col1','col2'] ]
```
#### Select by number
```python
select_one = df.iloc[num]
select_mul = df.iloc[num:num2]

```
#### Select Rows with Logic
```python
df[df.colName == 'some String' | df.colName2 != 4)
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc5MzEzNTUyNCw1NTU4Mzc1MDcsMjQ5Mj
IxODc2LC0xNDYzNzM5MTE3LC0yMTczOTcxMTAsLTYwODM2NDI1
OCwxODgyNzgzMjE3LDk1MzMyNDI3MCw0MzgyNjAwNjUsMTUxOD
AyMTc0OCwxNjQ2MTc1MjY0LDIwMjk4NzQ3MTMsLTE3MzY3MDY1
NjgsMTMwMzM2MjAwNywxMjg4NzU5NTAyLDg2MzIyNTYxNSwxOT
EyOTg1OTk3LC0xMjcxMDY3ODUwLDMxMzEzOTE4MF19
-->