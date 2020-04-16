## Lambda
```py
func = lambda x: x+1
>>> func(5)
> 6
# if statements
func = lambda  x:  [OUTCOME  IF  TRUE]  if  [CONDITIONAL]  else  [OUTCOME  IF  FALSE]

```



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

## Pandas
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
```py
 df1 = pd.DataFrame(['xxx,1].['yyyy',2], columns = ['string','num']
```
### Read/write CSV

```py
pd.read_csv('my-csv-file.csv')
df.to_csv('new-csv-file.csv')
```

 ### Inspect DataFrame
```py
# first 5 rows Default
df.head()
# Some stat
df.info()
```
### Selecting columns

#### Select by name

```py
select_one_cpl  = df['col1']
select_mul_col = df[ ['col1','col2'] ] 
```

#### Select by number
```python
select_one = df.iloc[num]
select_mul = df.iloc[num:num2]
```
### Select Rows with Logic
```python
df[(df.colName == 'some String') | (df.colName2 != 4)]

# Using .isin
df[df.ColName.isin(['str1','st2'])]
```

### Setting indices

rest_index(drop, inplace):

 - drop : 
	 - True/False = Drop/Keep old index
 - inplace :
 	 - True = Make changes on current df
 	 - False = return a new df 
```py
df.reset_index(drop = True, inplace =True)
```
### Add new data to df
```python
# To set all data in col to a single value
df[col_name] = newData  
# To set data in col to diffrent values
df(col_name) = [val1,val2,val3]
# Using math to create a enw col
df(col_name) = df[col_name_other] * 2

```

### Using Functions on a column with ( .apply )
```python
df[col_name] = df.col_name.apply(upper)  
```

### Lambda use on column 
```py
df['Email Service Provider']  = df.Email.apply(  lambda  x:  x.split('@')[-1] )
# OR
get_email_sp = lambda name:  name.split(' ')[-1]
df['Email Service Provider'] = df.Email.apply(get_email_sp)
```

### Lambda use on a row
```py
df['Price with Tax'] = df.apply(lambda  row:  row['Price'] * 1.075 if row['Is taxed?'] == 'Yes'  else  row['Price'],  axis=1 )
```
### Renaming columns  with ( .columns ) and (.rename)
```py
# Overwrites existing names - must have all columns 
df.columns = ['New name', 'New name2']

#.rename
df.rename(columns={ 'name':  'First Name',  'age':  'Age'},  inplace=True)
# Misspelling one of the original column names, won't produce an error. It just won’t change anything
# Uses a dict Object so use {}
```
### Calculating Column Statistics

```py
df.column_name.command()
```

|Command | Description|
|-|:-|
|`mean`	|Average of all values in column
|`std`|Standard deviation
|`median`|Median
|`max`|Maximum value in column
|`min`|Minimum value in column
|`count`|Number of values in column
|`nunique`|Number of unique values in column
|`unique`|List of unique values in column
|`isnull`| Returns true if value stored is null


### Calculating aggregate functions (.gorupby)
```py
df.groupby('column1').column2.measurement()
#Or multiple col
df.groupby(['column1','column2']).column3.measurement()

# Transform a Series into a DataFrame and move the indices into their own column.
df.groupby('column1').column2.measurement().reset_index()
```

### Pivot table

```py
df.pivot(columns='ColumnToPivot',index='ColumnToBeRows',  values='ColumnToBeValues')
```

### Inner Merge
```py
new_df = DataFrame1.merge(DataFrame2)
# OR
new_df = pd.merge(DataFrame1, DataFrame2)
# would merge df1 to df2 and then the new one to df3
new_df = DataFrame1.merge(DataFrame2),merge(DataFrame3)
```
###  Merge on Specific Columns using (.rename)
```py
pd.merge(df,col.rename(columns={'id': 'new_id'}))
```
### Merge on Specific Columns using (left_on, right_on)
Start merging with the df on the left with the df on the right
```py
 pd.merge(orders,customers,left_on='customer_id', right_on='id')
```
#### Using (suffixes) to avoid ambiguous names for merged columns
The default values are '_x',  '_y'  etc
```py
pd.merge( orders, customers,left_on='customer_id', right_on='id', suffixes=['_order',  '_customer'] )
```
### Merge two df with data not included in both df
#### All data (how = 'outer')
```py
pd.merge(company_a, company_b, how='outer')
```

```py
pd.merge(company_a, company_b, how='left')
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUxNzM4MjMwNiw1Njg0NjEzMTMsLTM0Nj
AyMzUxNSw3OTY5NzMzMSw2OTUyNTg4NDksMTk5Nzg3NTgzMiwt
MTE4MDgyMDk4MywxMDA5Nzk5MTY4LC05OTE2NjI0NDAsLTE4ND
I2NzM3MDgsLTEzNDE5NjEwNTAsMTUwMjUyNzM0NywtMTEzMjg3
NTI2MiwtMTk2OTg4MjQ2MSwxMzM2MTY2MjI0LDE2OTk4NDA0ND
YsLTExODU4MTU4MDYsLTE5NDYzNDU5NzksNTIyNzgzODA2LDEx
MDA3MjY3MzBdfQ==
-->