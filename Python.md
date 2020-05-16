## External successors

|Name|Link  |
|:--|:--|
|Formatting style guide   | pyformat.info |



## Writing style

Short strings would use a single `'`
Long strings should use a double `"`


## Print 
### `(.format) and print(f'')`
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
#### Using `%s` instead
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


###  Running pyhton
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

### Files `.open`
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

### Using Unicode `.encode`  and `.decode`

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

## `map`
```py
def square(num):
    return num **2
 nums = [1, 2, 3, 4]
 for item in map(square,nums):
     print(item)
 # 1
 # 4
 # 6
 # 16
```
## `filter`
```py
num = [1, 2, 3, 4]
list(filter(lambda n:n % 2 = 0, num))
# [2, 4]
```

#### `exec` - runs a string as python
```py
exec ('print("Hello")')
# Hello
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
### `.pop(num)`
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
### `sets`
#### `.sort()` and `sorted()`
`my_list.sort()` - will sort the current list changing it.
`sorted(my_list)` - returns a sorted list


- They don't have a particular order
- Only store unique values
- Can be used with `lists` to find unique values
```py
my_set = set()
my_set.add('Val')
print(my_set('Mississippi'))
# >>> {'i', 'p', 's', 'M'}
```
#### `.difference(SET)`
Get the difference between two `sets`
#### `.difference_update(SET)`
Update a set with the different items in another `set`
```py
s1 = {1,2,3}
s2 = {1,4,5}
s1.difference_update(s2)
s1
# OUPTUT {2,3}
```
#### `isdisjoint(SET)`
Are the two sets different

#### `.issubset(SET)`
Is a set a subset of another

## Loops

### Flatting the `for` loop
```py
mystring = 'abcde'
mylist = []
for letter in mystring:
    mylist.append(letter)
# Can be chagned to ..
mystring = 'abcde'
mylist = [letter for letter in mystring]
```
#### Perform any kind of calculation
```py
# EXAMPLE - the range of 1 - 10 squared
num = [num**2 for num in range(10)]
```
#### Add an `if` statement
```py
# Get only even numbers in a range of 0 -10	
num = [num for num in range(11) if num % 2 == 0]
```
#### Add an `if-else` statement
```py
# Get  even numbers in a range print 'ODD' if not even
num = [num if num % 2 == 0 else 'ODD' num for num in range(5)]
print(num)
# >>> (0, 'ODD',2 ,"ODD',4)
```


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

### `zip`
Merge two or more `lists` together into a single `tuple`   would merge to the shortest list.
```py
ls = [1,2,3]
st = ['a','b','c']
for item in zip(ls,st):
    print(item)
 # >>> (1, 'a')
 #     (2, 'b')
 #     (3, 'c')
```
## Generators
### `yield`

Once called stores last value returns it and continue with calculation saving memory 

```py
def time_two(n):
	for x in range(n):
	    yield x * 2
	print("this is it")
 
for i in times_two(5):
	print(i)
#  OUPUT
#  2
#  4
#  6
#  8
#  10
#  This is it  
```
### `next(_generator)`
Iterates the generator 
Does not stop by itself
```py
def foo():
	for i in range(3):
		yield(i)

for num in foo():
	print(num)
# OUTPUT
# 1
# 2

gen = foo()
print(next(g))
# OUTPUT
# 0
print(next(g))
# OUTPUT
# 1
print(next(g))
# OUTPUT
# 2
print(next(g))
# OUTPUT
# <ERROR>
```
## Iterators
### `iter(object)`
Transform an object to an `iterator` object
```py
st = 'somthing'
st_itr = iter(st)
print(s_itr)
# OUTPUT
# s
```
## Class
```py
__init__ #crater class
__str__ #string
__del__ # Delete object
```

####  Working with packages
To set a directory to work as a package an empty `__init__.py` must be define in each directory
```
|_> code
|-> \someCode.py
---> PackageFolder
 |------> \__intit.py
 |------> \pacakgeName.py
```
#### To know if you run a file directily

```py
__name__ == '__main__'
``` 
would be `True`



## Error handling

* `try` - Block of code to be attempted
* `except` -  Block of code will execute in case there is an error in `try` block
* `else` - No error in code block
* `finally` - A final block of code to be executed, regardless of an error

```py
try:
    # Some code to try
except
    # Some error accord
    # run this code block
else: 
    # No error
    # Run this code
finally:
    # Run this code ALWAYS
```

`assert` -Verify if somthing is True.
```py
assert (1 == 2), "Error!"
# AssertionError: Error!
```
### Unittest 

```py
import unittest
import name_of_script
 
class  TestCap(unittest.TestCase):
    def  first_test(self):
        # Check somthing using the script
        self.assetEqual(result,somthing)
    #  Can add as many tests as needed
    #  By what they check and/or numbered
```

## Collections

### `Counter`
Creates a `dict` from a list were the keys are is the values and the values are the count of that value
```py
ls =[1,1,1,1,1,2,2,2,2,3,4,5,5,5,5,5]
print(Counter(ls))
# OUTPUT Counter({1: 5, 5: 5, 2: 4, 3: 1, 4: 1})
print(Counter("some text".split()))
# OUTPUT Counter({'some':1,'text:2})
```
### `.most_common(num)`
Get the most  common element `num` in  a counter `dict`

### Common patterns when using the `Counter()` object
```py

sum(c.values())                 # total of all counts
c.clear()                       # reset all counts
list(c)                         # list unique elements
set(c)                          # convert to a set
dict(c)                         # convert to a regular dictionary
c.items()                       # convert to a list of (elem, cnt) pairs
Counter(dict(list_of_pairs))    # convert from a list of (elem, cnt) pairs
c.most_common()[:-n-1:-1]       # n least common elements
c += Counter()                  # remove zero and negative counts
```

### Collections module

### `defaultdict`
Does not rise a `key error` flag if a key is not found
```py
dic = defualtdict(lambda: 0)
# returns 0 if no key is found 
```
### `orderedDict`


### `namedtuple`

Just like a normal Tuple only with named index.
Structure  
`NAME_OF_TUPLE = namedtuple('Name_of_tuple', 'Atr1  At2 Atr3')`
```py
Dog = nametuple('Dog','age breed name')
wolfee = Dog(age =2, breed ='Lab', name = 'Wolfee')
# Can then access wolfee.age, wolfee.breed and wolfee.name

```

### `datetime`

#### `datetime.date`
```py
dt = datetime.date(2020,3,10)
# can also holdes hour, min,sec
```
#### `datetime.time`
To work with a time stamp


### `pdb`  debugger
Interactive debugging environment 
```py
pdb.se_trace()
# opens a CLI to test 
# to quit press 'q'
```

### `timeit`
To test runinng time
```py
#timeit,timeit(
```

### Regular expressions
```py
import re

```

### `StringIO`
Makes a file object in memory
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTMwOTI2Mjk2NywxNTMzOTkwOTc4LC0xOT
IzMTIyOTc3LC0xNDg5NjY3NDAsLTE1NTg1NDExODksMzM3MjA2
MzU1LC0xODM4OTM4ODkzLDg2OTUyOTIyLDExMTk4MTM0MjEsLT
k3OTYzNDU5NywtMTY0MzM1MTYzMCwtMTY5ODcwODMyNCwtODU5
OTIzNjMyLC00NjI5NTI3MTEsLTY5OTg5NjE5MiwtMTY3MjAwMj
E1MCwtMzk0MjMzMzM0LC0xNjkzNzgxMzYzLDE2NjEzOTk2MjAs
NzgwMzkwMjE4XX0=
-->