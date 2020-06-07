

[toc]

	basicrobot.bill = New basicRobot2(2,6,east,1)
	bill.move


##Robots

bill

x-location =2
y-location  =6
direction = east
num-beepers = 1

1x + 0y = 0
3x + 0y = 0

final => const ver synetex{ final nameOfV TYPE = num/char

/ => div (gives out int for int/int if int/real = real)
% => mod

To roundup Real Ver -   .00   to roundup to two digits after the 

number

string ______ // To define a string ver

<code>
x,y int;
x=1
y = ++x  // x=1+1 then y=x result y=x=2
y = x++  // y=x then x=x+1  result y=1, x=2

###scanner mathod

** would only read non sparted string or num
** Use line with mathod to read entire line
nextInt() => reads int
next() => reads string


**string**

int length() - num of char //starts from 0
char charAt(int index) - return char # in string (from left)
string toLowerCase - trnasform to lower case entire string


**casting**

in order to 'fit' a double to int we use (int)


**syntax**


extends - class

solve the main problem then the rest
class NAME {

delarations    - instance varible => unique name,symbolic 

constant

constructor definitions - how to create and initialize objects

method definitions - how to manipulate those objects 

Two kinds of methods: 
Class methods and Instance methods lMath.sqrt is an example 

of a Class method; 
“Math” is the name of a class, and we invoke the sqrt method in 

that class l

main is also a Class method lI’m still not going to talk more 

about Class methods now; 
only Instance methods in this lecture


**Void**

if a method does not return anything it returns Void.

TYPE name_of_method(TYPE name_of_parameters...) 

The most important stage in writing a class is to get an 

abstraction of the class done first. 
What does an object of this type represent? 
What is its interface? 
 What is its internal state? 
This means you have to know what should be the internal state 

(variables) and also the behavior/interface (methods) of the 

class before you start to write your class code

**syntax**

constant varible - CAPITAL
local varible - _firstUnderscore

When we declare a variable of an object type, we get a 

reference in memory to an object (the object’s address); the 

object is stored elsewhere:


###Structure of a class


1. declaration of class attributes -> <code> private int _xyz;
2. constructor definition 	   <code> public c (int xyz ) { _xyz =  xyz;}
3. method definition


this  -> used to refer to the object issuing the method 

public String toString ()  -can be used to give a ANY string value 

to the object (name,summary etc)  , can be acceced using just 

object name

copy constractor -> in order to make an excet copy of an object

ClassObject obj1 = new  ClassObject(obj2); 


**import java.util.Random**
 
**nextInt (int)** - places a random number


**Aliasing impotent note**
-------------------------------

when  class has a method with an obejct:
If you receive as a variable, an object and you need to place it in a 
method -> make a copy (ie NEW) instead.- copy object method.
mmn12 -  3898330-20441 

for/while
-----------

statment1; // initialize
while(condition)   // condition
{
 statment3; //increment
statment2;

for (statment1; condiion; statment2; statment3;)
initialize

do 

.....

while (


array 
-------

Declaring an Array Variable
int[ ]  counts;
double[ ]  scores;
Time[ ]  appointmentTimes;

each array has a mathod : length- the number of elements

	counts  =  new int[10];
	scores = new double[15];
	appointmentTimes = new Time[10]; 

	int[ ] primes = {2, 3, 5, 7, 11, 13, 17, 19, 23, 29};  // must be in same line


	int[ ] primes;// *NOT ALLOWED
	primes = {2, 3, 5, 7, 11, 13, 17, 19, 23, 29};

**note;**
**In Java, a two-dimensional array is actually an array of arrays**

* When we write:

double[ ][ ] energyTable;
energyTable = new double[NUM_YEARS] [NUM_SOURCES];

* It is actually a shorthand way of writing

double[ ][ ] energyTable;
energyTable = new double[NUM_YEARS][ ];


----------


A Two Dimensional Array Can be Ragged (rows of different lengths)

    int[ ][ ] a = new int[3][ ];
    for (int i = 0; i < 3; i++)
      a[i] = new int[i + 1];
.

	for (int i = 0; i < NUM_YEARS; i++)
	  energyTable[i] = new double[NUM_SOURCES];
	

in two dimantional matrix:
The length of the rows need not be declared at the same time 

as the length of the columns:
Each of the Arrays Has its Own Public Attribute length
<code>m[][] = { {1,1}, {2,2,3} };
m.length = 2
m[0].lengh  = 3 



##unit 11

###subclass and protected

Class C is a subclass of a class B:

class C extends B {
…
}
Objects of C contain all instance variables of B as well as those 

of C, respond to all the instance methods of B as well as of C, 

and C can redefine methods and override instance methods 

defined in B


Using protected instead of private allows inheritance

super- for constractor superceds

static - makes a varible/method avalabile witout an object. 

*they can't access instent varibles of the class.



##unit 12

the physical location of a package affects what  
Java classes are placed into directories (or folders) on the 
computer 

- The classes in each directory form a package lThis 
helps organize classes, and also gives another way of 
controlling access among classes 
* Example: java.applet is the 
package of classes in subdirectory "applet" under the directory 
"java" (whose location varies depending on the system)
java.applet -> C:\java\applet\

12- 4 Direct Use of Java API Classl
To use, for example, the class Math in the package java.lang, it 

is possible to use the fully-qualified name: 
example:
x = java.lang.Math.sqrt(3);

-----
Of course, it's more convenient to do it the way we've been 

doing it, using the import statement; either

import  package_name.class_name;

or

import package_name.*; 

java.lang.*; //always in.


* All of the .class files placed in one directory belong to the 

same, unnamed package 
* To cause a class to be placed in a particular named package: 
** Put the .class file in the appropriate directory ** Compile the 

class with the package statement, which must be the first non-

comment line in the Java source file:

package  package-name; 


**visibility**

* A public instance variable is visible to all other classes 
* A private instance variable is visible only to the methods of its 

class 

* If it is declared neither public nor private, then it has 
"package visibility"; it is visible to methods defined in 
subclasses, or in other classes, in the same package as its class

**Similarly for Classes**

* A class declared public is visible to all classes
* A class not declared public is visible to the classes in its own 
package 
* A class cannot be declared private

###Protected

* We might want to give all subclasses access to variables and 
methods without allowing clients to have access 
* That's the purpose of another category of accessibility: 
protected 
* Members declared protected are visible to other classes in the 
same package, and to subclasses in the same package and 
other packages, but not to clients in other packages 
Inherited Visibility - object obtain method/varible
Direct Access Visibility

|Modifier    |Class|Package|Subclass|World|
|:-----------|:---:|:-----:|:------:|:---:|
| public     |*Y*|*Y*|*Y*|*Y*| 
| protected  |*Y*|*Y*|*Y*|*N*|
| no modifier|*Y*|*Y*|*N*|*N*|
| private    |*Y*|*N*|*N*|*N*|


super(insted of class name)//can be also this, 
if a superclass doesn't have a zero-argument constructor, the 
subclass must explicitly call the superclass's constructor with 
arguments 

_evey parent can contain a child._



###Upcasting

* Why didn’t we have to explicitly cast
Bird, Dog and Fish to Animal when we
put the instances into the array on the
previous slide?
* Because this is upcasting – casting
from a derived class to a base class –
and Java does it for us automatically
* You can also write it explicitly if you
want (no harm done)
  

<code>boolean instanceof 

The keyword *instanceof* is used to ask an object if it is an 
instance of the specified class

if we use polymorphism in order to use a subclass we need to 
cast it.

###Sub-classes as Sub-types
* We can view a RestrictedFile object from 3 different points of 
views: 
 1.   As a RestrictedFile. This is the most narrow point of view (the most specific). This point of view ‘sees’ the full functionality of the object. 
2.  As a File. This is a wider point of view (a less specific one). We 
forget about the special characteristics the object has as a 
RestrictedFile (we can only open and close the file). 
- As a plain Object.

###abstract

This “prototype” is included in the Mouse class 

* "abstract" tells Java that makeMove( ) is expected to be defined in a subclass 
* Any class that includes an abstract method is itself abstract, 
and has to be declared abstract itself 
* Such an abstract class cannot be instantiated by a client, you just have to subclass it and define its abstract methods 
* So the Mouse class will be 

###Syntax Differences

* Classes that contain real definitions of these abstract methods 

write "implements interface_name" instead of "extends…" 
* All the methods in the interface are abstract, so you don't 
write "abstract" in front of them 
* All symbolic constants are assumed to be public, static, and 

final, so don't write those keywords, either. Sometimes 
interfaces are used to give definitions of symbolic constants to 
be used in several classes

##unit 13

###Exceptions in Javal

Java actually uses the notion of exception for 3 related (but 
different) purposes: 
1. Errors: an internal Java implementation error was discovered 
E.g: out of memory 
2. Runtime exceptions: a programming logic error was discovered vE.g. division by 0 * Checked Exceptions: an exceptional case was discovered (E.g. file not found) 

###try, catch, finally

* The try clause establishes a block of code that might have 
exceptions or abnormal exits 
* The try block is followed by zero or more catch clauses that specify code to handle various types of exceptions 
* the finally clause specifies code that will always be performed, 
if any part of the try block is executed (good for cleanup, closing files, etc.)

###Declaring Exceptions

Certain kinds of exceptions need to be declared in a method’s 

declaration, if they are not handled inside the method:
public void open_file( ) throws IOException {
// Statements that might generate an
// uncaught java.io.IOException
} 
* You only need to declare exceptions that are not subclasses 

of Error or of RuntimeException; these are just too common to 

require declaring 
*An example that does not need to be declared is 

ArrayIndexOutOfBoundsException

###unit 14

####Five Different Search Methods
* **search** searches component-by-component through an unordered array. 
* **stateSearch** is a state-oriented version of search 
* **linear searches** component-by-component through an ordered array. lquadratic is like linear, but takes bigger jumps 
* **binary** uses a divide-and-conquer algorithm, and is the fastest of all


```
int search (int[ ] data, int num)  
	{   //  Search method For an unordered array. 
		//   Return -1 for absent number. 
	int  pos = 0; // position of current component 
	
	while ( (data[pos] != num) && (pos <(data.length - 1)) ) 
		pos++; //Postcondition:if data[pos] isn’t num, no component is. 
	if (data[pos] == num) return pos; 
} // end of search
```

###Similar Idea, but use a State-Oriented Approach
We’ll use the states FOUND, ABSENT, and SEARCHING to control our loop and to let us know the status of the search. lGoal: Locate a value, or decide it isn’t there. lBound: Our state is either ABSENT or FOUND 
Plan: Advance to the next component.     Update the state




 
	int stateSearch(int[ ] data, int num){  
    // State-oriented search of unordered array. 
    // Return -1 for absent num   
    	int pos = 0, state = SEARCHING; 
    	do {   // until we’re not searching anymore   
    		if (pos >= data.length) state = ABSENT; 
    		 else  if  (data[pos] == num) state = FOUND;
    			   else  pos++; 
    		} 
    	while ( state == SEARCHING) ; 
    	// Postcondition  if num was there, state’s FOUND and data[pos] is num 
    	switch (state) { 
    	case FOUND:  return pos; 
    	} 
    } // end of stateSearch

###Searching Ordered Arrays

* When we had unordered arrays, we had to look through (potentially) every component to find the value we were looking for 
* With ordered arrays, we can be more clever; we look at three techniques: 
	* linear 
	* quadratic 
	* binary
####Linear Search 

* Very similar to the “search” method before, but stop the search if we find a component beyond the size of the one we are looking for.


####Quadratic Search


    int quadratic(int[ ] data, int num){  
    // Quadratic search through an ordered array. Return  
    		   // -1 for absent num 
    		final int FOUND=0, ABSENT=1, SEARCHING=2, 
    			CLOSE_ENOUGH=3; 
    		int  state = SEARCHING, position = 0, jumpSize; 
    		jumpSize = (int) (Math.sqrt(data.length)); 
    		do {   // by big jumps until we’re close enough    
    			if  ( (position + jumpSize) >= data.length) 
    				state = CLOSE_ENOUGH;    
    			else  if  (data[position + jumpSize] > num ) 
    				state = CLOSE_ENOUGH;    
    				  else  position = position + jumpSize; 
    			} while (state != CLOSE_ENOUGH); // Postcondition: 
    			// if num is there, data[position] <= num 
    			state = SEARCHING;  // reset the current state 
    			do {  
    			// by single steps until we’re not searching 
    				if (position >= data.length) 
    				 state = ABSENT; 
    				else if ( data[position] > num ) 
    				 state = ABSENT; 
    				     else if ( data[position] == num ) 
    				      state = FOUND; else position++;  
    				      // state is unchanged 
    				} while (state == SEARCHING);  
    				// Postcond. if num's there, state’s 
    				// FOUND and data[position] is num 
    				if (state == ABSENT) return  -1; 
    				else return position; 
    } // quadratic

####The Binary Search

    int binary (int[ ] data, int num) 
    {    // Binary search for num in an ordered array   
    int  middle, lower = 0, upper = (data.length - 1); 
    do { middle = ((lower + upper) / 2); 
    if (num < data[middle]) upper = middle - 1; 
	    else lower = middle + 1; 
	    } 
    while ( (data[middle] != num) && (lower <= upper) ); //Postcondition: if data[middle] isn’t num, no
    // component is 
    if (data[middle] == num) 
	    return middle; 
	else return -1; 
    }  // binary


log2n - 1

###Run time
* O(1) = a fixed number of operations
* n^2 = a nested loop

###sorting

* Select is based on selection sorting 
* Insert is based on insertion sorting 
* Bubble is based on bubble sorting 

**select**
search through array, find largest value, exchange with first array value: do the same for second

** insertion sorting **
- move through the array, keeping the left side ordered; when we find the 35, we have to slide the 18 over to make room
- continue moving through the array, always keeping the left side ordered, and sliding values over as necessary to do so.

###Each Method’s Advantages

* Selection sort is simple because it requires only two-value exchanges 
* Insertion sort minimizes unnecessary travel through the array. If the values are sorted to begin with, a single trip through the array establishes that fact (selection sort requires the same number of trips no matter how organized the array is) 
* Bubble sort requires much more work, but…well,…uh,…it’s the easiest one to code!  **never used very inefficent**

    void select (int[ ] data) {    
    // Uses selection sort to order an array of integers.   
    int  first, current, largest, temp; 
    for (first = 0; first < data.length - 1; first++) 
    { 
    largest = first; 
    for (current = first + 1; current < data.length; current++) 
    {      
    if ( data[current] > data[largest] )
    largest = current; 
    } // Postcondition: largest is index of largest item 
    // from first..end of array 
    if (largest != first) 
    {   // We have to make a swap 
    temp = data[largest]; 
    data[largest] = data[first];   // Make the swap 
    data[first] = temp; } 
    } 
    }  // select


    void insert (int[ ] data) {   
     // Uses insertion sort to order an array of integers. 
     int  newest, current, newItem; 
     boolean seeking; 
     for (newest = 1; newest < data.length; newest++) { 
	     seeking = true; 
	     current = newest; 
	     newItem = data[newest]; 
	     while (seeking) { 
	     // seeking newItem's new position on left      
		     if (data[current - 1] < newItem){  
			     data[current] = data[current -1];
			     //slide value right  
			     current--;
				 seeking = (current > 0);       
				}       else seeking = false; 
			}  // while 
		// Postcondition: newItem belongs in data[current] 
	data[current] = newItem; 
	}  // newest for 
}  // insert


void  bubble (int[ ] data) {    // Uses bubble sort to order an array of integers. int  last, current, temp; for (last = data.length-1; last > 0; last--) { for (current = 0; current < last; current++) { if ( data[current] < data[current + 1] ) { temp = data[current]; data[current] = data[current + 1]; data[current + 1] = temp; }  // if }  // current for //Postcondition: Components last through the end of
// the array are ordered. }  // last for }   // bubble


###Delayed Evaluation

###Tail Recursion 
With tail, or end, recursion, there is nothing left to do after the last call. No unfinished statements have been left on the stack. 

###More Recursive Sorting: Quicksort 
* Quicksort is an O(n^2) algorithm in the worst case, but its running time is usually proportional to n log2 (n); it is the method of choice for many sorting jobs 
* We’ll first look at the intuition behind the algorithm: take an array


###How to pick the median value
* There are many techniques for doing this. In practice, one good way of choosing the pivot is to take the median of three elements, specifically a[lo+1], a[(lo+hi)/2], and a[hi] 
* We’ll choose their median using the method medianLocation( )

    int medianLocation(double[] a, int i, int j, int k) { 
    if (a[i] <= a[j]) 
	    if (a[j] <= a[k]) 
		    return j; 
	    else 
		  if (a[i] <= a[k]) 
			  return k; 
		`	  else 
			  return i; 
	else // a[j] < a[i] 
		 if (a[i] <= a[k]) 
			 return i; 
		  else 
			  if (a[j] <= a[k]) 
				  return k; 
			  else 
				  return j; 
	}

### Lists

```
class Node {  int _data; 
 Node _next;
 }

Node firstNode = new Node( ); 
firstNode._next = new Node( ); 
firstNode._next._next = new Node( ); 
firstNode._next._next._next = new Node( ); firstNode._next._next._next._next = null;
```

class ListNode  {
private int _value;
private ListNode _tail;

public ListNode (int v, ListNode next) {
_value = v; _tail = next;
} public int getValue ( ) {return _value;} public ListNode getTail ( ) {return _tail;}
}

* the connected list needs to be built form LAST to the first one because of *null* value
```
ListNode list = new ListNode(-14, null);
list = new ListNode(616, list); 
list = new ListNode(10945, list); 
list = new ListNode(17, list);
```

* With each line, **list** points to one node further to the left

**embedded form**

```
ListNode list = new ListNode(17, 
new ListNode(10945, 
new ListNode(616, 
new ListNode(-14, null) ) ) );
```  

### Queues, Stacks, Trees

### Basic Link Manipulation
* maintaining auxiliary pointers to different parts of a list (especially first and last nodes) 
* adding to the end of a linked list 
* traveling through an entire list 
* searching for a particular node 
* inserting into the middle of a linked list 
* merging two lists together or inserting one list into another 
* deleting individual nodes or sublists

Let’s say we want to insert a node right after the node pointed to by current
```
temp = new Node( ); 
temp._data = 3000; 
temp._next = current._next; // order is crucial 
current._next = temp;
```

### Size of a list
````
public int length ( ) {
		if (_tail == null)
			return 1;
		else
		 return ( 1 + _tail.length( ) );
}

### Adds a new node to the end of the list
```
public void addToEndM (int n) {
	if (_tail != null)
// we're a cell in the middle of the list
		_tail.addToEndM(n);
	else // we're the last cell
	 _tail = new ListNode(n, null);
}
```

### Add a node in an ordered list with no duplicates
```
public ListNode addInorderM (int n) {
	if (n < _value)
	 return ( new ListNode(n, this) );
	else if (n == _value)
		  return this;
		 else if (_tail == null) {
			  _tail = new ListNode(n, null);
			   return this;
			  }
			  else {
				_tail = _tail.addInorderM(n);
				return this;
			  }
}
```

####MergeSort 
* Exploits the same divide-and-conquer strategy as QuickSort 
* Better suited for linked lists 
* Divide the linked list in 2 nearly equal-sized parts
* Recursively MergeSort the 2 halves 
* Merge the two halves back together
```
ListNode merge (ListNode L) {
  if (L == null)
	return this;
  if (_value < L._value)
	if (_tail == null)
	 return new ListNode(_value, L);
	else
	 return new ListNode(_value,  _tail.merge(L));
   else 
	return new ListNode(L._value,  merge(L._tail));
}
```
MergeSort is O(nlog_2n) always
QuickSort, in contrast, has this performance on average, but can also have quadratic ( O(n^2) ) performance, worst case 

### Methods for writing if then

**Instead of**
```
//_return the largest number
if (a > b)
 return a;
else
 return b;
```
**You can write**
```
return (a > b ? a : b);
```
### Binary  search types
* **PostOrder** - Left child ->  Right child -> Father(root)
* **PreOrder** -  Father(root) -> Left child -> Right child
* **InOrder** - Left child -> Father(root) -> Right child
* 

search (s,a,b) 



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkxOTA5OTczNl19
-->