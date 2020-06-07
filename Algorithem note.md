
###Binary Search 

####Recursive

```
BinarySearch(A, p, q, key)
1. if p > q ► base case: empty array
2.    then return –1
3.    else mid ← floor((p + q) / 2)
4.       k ← A[mid]
5.       if key = k
6.        then return mid ► found!
7.        else if key < k
8.              then return BinarySearch(A, p, mid – 1, key)
9.              else return BinarySearch(A, mid + 1, q, key)
```

####Iteration
```
BinarySearch(A, p, q, key)
1. while p ≤ q ► the sub-array to search is not empty
2.    do mid ← floor((p + q) / 2)
3.      k ← A[mid]
4.      if key = k
5.       then return mid ► found!
6.         else if key < k
7.              then q ← mid – 1
9.               else p ← mid + 1
10.  return –1 ► not found 
```
#####**Run time**
**h = log n **

###Sorting problem

* General methods - bubble,sort, selection sort etc.
* With a pre condition to the type of input - counting-sort,radix-sort,bucket-sort



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5OTk1NjE5M119
-->