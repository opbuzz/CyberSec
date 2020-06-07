

```
BinarySearch ( A , z , low, high,goLeft,found)
01  found = NIL
02  while low <= high
03	  mid = Round_down((low + high)/2)
04	    if z == A[mid] then
05		  found = mid
06		  if goLeft == TRUE then
07		    high = mid -1
08		  else
09		    low = mid + 1
10		else
11		  if z > A[mid] then
12		    low = mid + 1
13		  else
14		    high = mid - 1
15  return found 

01  BinarySearchMain (A, z,left,right)
02    left = BinarySearch(A , z , 0, A.length,TRUE)
03    if left == NIL
04      right = BinarySearch(A , z , 0, A.length,FALSE)
05    else
06      right = BinarySearch(A , z , left, A.length,FALSE)
  

	
	while low <= high
		mid = Round_down((low + high)/2)
		if i == A[mid]
		  return mid
		else
		  if i > A[mid]
		    low = mid + 1
		  else
		    high = mid - 1
	return NIL  
```


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbOTU1Nzk0NTgxXX0=
-->