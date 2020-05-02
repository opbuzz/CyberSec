## External successors

|Name|Link  |
|:--|:--|
|Formatting style guide   | pyformat.info |



## Writing style

Short strings would use a single `'`
Long strings should use a double `"`


## Print 
### Using (.format) and print(f'')
```py 
x = 5
y = 2
print(f'this is {x} and {y}'
# Output -> this is 5 and 2
#OR
print('this is {x} and {y}'.format(x,y)
#Better
print("this is {first} and {second}".format(first= x, second = y))
```

If you use `{}` in a string,  each call with .formatter would change its values
```py
text = "It is a {}"
print(text.format('kite')
# Output -> it is a kite
print(text.format(5))
# Output -> it is a 5
```
#### Using %s instead
```py
text = "It is a %s"
print(text, "%s",%"kite")
# Output -> It is a kite```
```
### Input from user
If `end = ' '` then then `print()` will not end the line with a newline
```py
print("Your name?") 
name = input(name, end =' ')
print("You are called {name}")
# OR without the end = ''
name = input("Your name?")
print("You are called {name}")   
```

### When there is only one variable 
```py 
x = 5
print('this is {x}'
# Output -> this is 5
```
### Escape characters
|Escape| What it does  |
|:-|:-|
`\newline`|Backslash and newline ignored
Backslash (`\`)|print("\\")
`\'`| Single quote (`'`)|
`\"`| Double quote (`"`)
`\a`| ASCII Bell (BEL)
`\b`| ASCII Backspace (BS)
`\f`| ASCII Formfeed (FF)
`\n`| ASCII Linefeed (LF)
`\r`| ASCII Carriage Return (CR)
`\t`| ASCII Horizontal Tab (TAB)
`\v`| ASCII Vertical Tab (VT)
`\ooo`| Character with octal value ooo
`\xhh`| Character with hex value hh
`\N{name}`| Character named  name  in the Unicode database
`\uxxxx`| Character with 16-bit hex value  xxxx. Exactly four hexadecimal digits are required.
`\Uxxxxxxxx`| Character with 32-bit hex value  xxxxxxxx. Exactly eight hexadecimal digits are required.


###  Runing pyhton
Any text after running  `python`in cmd would be considerd as a string
```py 
# Runing this
from sys import argv
script, first, second, third = argv
rint("The script is", script)
print("First",first)
print("Second",second)
print("Third",third)

#  /.pyhon file.py one two three
#  The script is file.py
#  Fisrt one
#  Second two
#  Third Three 
```

### Files (.open)
- `close` - Closes the file
- `open` - You can open a file multiple times.  if  a file is opened with a 'w'  then it will delete all the content of the file
- `read` - read the content of a file - returns an object
- `readline` - Read one line
- `truncate` - Empties the files
- `write('somthing')` - Writes string to the file.
- `seek(offset = NUM,  whence = 0,1,2)` - `0` - moves read/write location to the beginning of the file. `1` - current position _(For non text files use)_ .   `2` - the end of the file


### Checking if a file exists
```py
from os.path import exists
filename = 'text.txt'

print(f"Does the file exist? {exists(filename)}")

# Does the output file exist? True

```

### Using Unicode (.encode)  (.decode)

Decode bytes
Encode Strings
`str.encode()`  returns a `bytes` representation of the Unicode string, encoded in the requested _encoding_.

The opposite method is `bytes.decode(decode)`
```py 
languages = open("languages.txt", encoding = "utf-8")
```
#### Using pointers *

```py
formula = (10, 40, 60)
print(f"We'd have {beans} beans, {jars} jars, and {crates}, crates.")
### the
print("We'd have {} beans, {} jars, and {} crates".format(*formula))
```
### Floating point precision printing
Float formatting follows `{value":witdth/precision f}`
* Width  - how much long is the string  including the `.` (prints blank spaces if not enough char)
* Precision -  the precision of the number shown
```py
num = 1/7 
# num =0.14285714285714285
print("{val:0.2f}".format(val= num))
```
### Files 
Use the `with` statement so the file would close automatically 
```py
with open('fileName.txt') as my_file:
	# Some commands
```
## Tricks
####  Checking if a number is in range
```py
>>> num = 10
>>> 1 < num < 20
# TRUE

# OR
>>> num = 10
>>> num in range(20)
# TRUE
```
#### Printing a string in reverse
```py
st = "abcdefg"
print(st[::-1])
# OUTPUT -> gfedcba
```

## Lambda
```py
func = lambda x: x+1
>>> func(5)
> 6
# if statements
func = lambda  x:  [OUTCOME  IF  TRUE]  if  [CONDITIONAL]  else  [OUTCOME  IF  FALSE]

```
#### Common functions
`exec` - runs a string as python
```py
exec ('print("Hello")')
# Hello
```
`assert` -Verify if somthing is True.
```py
assert (1 == 2), "Error!"
# AssertionError: Error!
```
`try` -  Try block, if exception go to `except`


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
### .pop (Num)
```py
my_lst = ['a','b','c','d']
lst.pop()
# >>> 'd'
lst
# >>> ['a','b','c']
lst.pop(0)
# >>> 'a'
lst
# >>> ['a','b'] 
```
### .sort() and sorted()
`my_list.sort()` - will sort the current list changing it.
`sorted(my_list)` - returns a sorted list

 
## Sets
- They don't have a particular order
- Only store unique values
- Can be used with `lists` to find unique values
```py
my_set = set()
my_set.add('Val')
print(set('Mississippi'))
# >>> {'i', 'p', 's', 'M'}
```

## Loops

### Enumerate
Returns a `tuple` with an index
```py
st = 'abc'
for index, letter in enumerate(st):
    print(index, ' ' , letter)
 # >>> 1 a
 #     2 b
 #     3 c
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
### Uses DataFrames which are like spreadsheets

```python
import panda as panda
```
### Using dictionary 
Each key is a column name and each value is a list of column values. The columns must all be the same length or you will get an error
```python
 df1  =  pd.DataFrame({'string':['xxx',  'yyy'],
'num':[1,  2]})
```
### Using Lists
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
#### All columns (how = 'outer')
```py
pd.merge(company_a, company_b, how='outer')
```
#### Compare data from a specific column to another (how = 'right')') OR  (how = 'left')
```py
# All rows from the left df would be showen but rows with no values wuold return a NaN
pd.merge(company_a, company_b, how='left')
pd.merge(company_a, company_b, how='right')
```
## Concatenate DataFrames (.concat)
```py
dp.concat([df1, df2])
```



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MjA3NTg1MzcsLTI1OTk4NDcwLDQ3Nz
c4MjE4Myw1NjU0NzM2MjIsMzYwNzgxODQ2LDE0MDc5MTI4LC0z
Nzk2MjIxMTEsLTIwNjUxNTgwNCwxNDAxMjgxMjY0LDExMzEzOT
kyODksLTE1NTIwODM3MzIsLTIwMzMzNjk4NTYsLTE0OTMwNTMw
NjIsLTE1ODI1ODQwNjAsODEyNTI4Nzk5LDE2NTkxMDUzMjgsNz
A1NjgxNjY5LDkwMjQ4NDUwNiwxNDk5ODc2MjEzLC00NjAxMzIy
OF19
-->