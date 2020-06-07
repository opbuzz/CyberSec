

#### Syntax - 
**Function prototype**  - needs to be defines  in order use function anywhere in the program 
```
/*.function prototype*/
char f1(int,char);
/*no need to define the name*/
int f2(int a[],int n);

int main(){

	....
}
/*Actual function.*/
char f1(int x, char h){
	...
} 
int f2(int w[],int k){
	...
}
```
### Consent variable 
```
#define somevalue = 100;
```

### Variable definition 
#### Global 
* Can be declared ANYWHERE between functions.
* Can be accessed by function IF they are declared before it.
* In case there is duplicate name (global and local) the function would use the local one.
* set to zero / null by default. (*not true for local variable*)

#### Array
* if assigned for only part of the array size, the other cells would be set to zero.
``` 
int c[5] = {1}
/* the array would be [1,0,0,0,0]*/
```


#### Prototype/function
* a function can access a other function ONLY IF it holds it's prototype.
*


## Standard Library
* **stdio.h** - input/output
* **math.h** - math operations
* **stdlib.h** - dynamic allocation and more
* **ctype.h** - character manipulation
* **string.h** - string manipulation.
* **stdarg,h** - variable-length argument list.

## Variable Types
| char | int | float | double | void |
|-|

By default all int are _signed_

### construct new types using
| struct | enum | union | typedef |
|-|


### Type modifier (not for void)
| signed | unsigned | long | short | static | extern | register | auto
|-|



###Function
* **printf("STRING")**
* **scanf("%d %u %f ....",&input1,&input2...)**
	* return (0 - no valid input,  >0 - the number of valid inputs, -1 EOF - the end of input)

**additions**
	 
	%d - signed int
	%u - unsigned int
	%f - real number
	%o - unsigned int (8 bit)
	%x -  unsigned int (16 bit)
	%c - single char
	%s - string


* **for(init ; condition, ; increment)**
	* exp - for(;;)  = infinite loop

**additions**

	continue - go to the top of the loop without executing the rest. 
	break - stop loop

* switch (expr) 
	case const -expr1 ... break;
	case const -expr2 ... break;
	default  : ....;

### Linux

| general | function |
|-------|-----------|
|./ |run a program|
|./ ProgFile < DataFile | get input for the program from DataFile|
|./ ProgFile > OutputFile | capture output in a file instead of screen|
|cat | print file on screen|
|**gcc** | |
| -ansi | check ansi standard |
| -o | compila e object file |
|-c| compile source files to object files without linking|
|-Dname[=value] |	define a preprocessor macro|
| -fPIC|	generate position independent code for shared libraries|
| -glevel | generate debug information to be used by GDB|
| -Idir	| add include directory of header files|
|-llib | link with library file|
|-Ldir | look in directory for library files|
| -o output file| write build output to output file|
| -Olevel |optimize for code size and execution time|
| -shared | generate shared object file for shared library|
|-Uname| undefine a preprocessor macro|
| -w | disable all warning messages|
|-Wall| enable all warning messages|
|-Wextra| enable extra warning messages|
| -lm | in order to use  math.h |



#### Signed and Unsigned
* The first cell that defindes if a number is negative or positive called MSB (most important Bit)
*  The last cell is called LSB(least important Bit)

#### Orators

```
1) ~ not
2) & and
3) | or
4) ^ xor
5/6) >> right shift
5/6) << left shift
``` 
 
**unsigned only**
shift right = divide by 2
shift left =  multiply by 2
 
### show binary number
```
sizeof(int) * 8  // to get the number of bits

void f(int x)
{
  int x;
  unsigned mask;
  mask = 1<<(sizeof(int)*8-1);
  printf("\n enter num :\n");
  scanf("%d",&x);
  while(mask)
  {
     printf("%d_",(x&mask)?1:0);
     mask>>=1;
  }
```

The expression :
```
 num >>= (sizeof(int)*8-1)
```
splits in to two option depending if the int is **signed** or **unsigned**

If sigend     =  num is 1111 1111
if unsigned =  num is 0000 0000 


#### Functions

getchar() - returns int, when there is no more char return EOF (=-1)
putchar() - prints int
puts(string) - prints a entire string
```
int ch;
while(ch = getchar())!=EOF){
  //somthing
}
``` 
##### enum
	#define sun =1 ;
	.
	.
	.
	enum numbers{x,y,z} // sets x=1 ,y=2, z=3;
	enum scales{a = 70 ,b,c=87} // sets a=70,b=71,c=87
	
	int number = x; // sets it to 1
	int scale = b;  // sets it to 71
 
When crating multiple file program you can only access a function in another file, if it is declared in current file's  prototype.


### Type of variable -static

* Global - the var can only be acceded locally in the file it is defined.
* Local - the variable is created once, becomes a "global" just for the function (the value is kept) 
* if assigned to a function it becomes protected (JAVA)


example
```
void g(); 
void h(); 
main()
  {
   g(); // x= 10
   g(); // x= 10
   g(); // x= 10

   h(); // x= 10
   h(); // x= 11
   h(); // x= 12

}

g()
{
   static int x = 10;
   x ++;
}   

h()
{
   int x = 10;
   x ++;
}   

```
#### file type - Header .h


* no defections of functions, only declarations.
* 
<stlib.h> 
### Function
* atof() - transforms an array of char to a float number. (Ascii To Float)
* * atoi() - the only with integer
 example 
```
'123'  -> 123.0
'1.587 -> 1.587
'148.7abs' -> 374.1  /*until it gets a non digit*/
```



<ctype.h>
### Function
* isdigit() - returns true if char is a digit 


##### Pointers

```
int x = 480; /* Change value*/
int *p;   /* Define a pointer that points to an integer*/
p = &x;   /* get value address */
printf("%d",*p); /* would get the value of x */

/* casting*/
double *q;
q = (double *)p;
printf("%d",*((int*)q));

```

A pointer would point to next place in the memory depending on its size.

#### Array

* Array = static pointer - var[num]   - number has to be a known number.  _var_ would always point to the first number of the array.
```
int a[5] = {10,20,30,40,50};
int *p;
p = a;
printf("%d",* (p+3)); /*returns 30 or a[3]*/
printf("%d", a[2]);  /*returns 20 or a[2]*/
printf("%d", *(a+2)); /* works the same way as above*/
printf("%d", p[2]);  /*returns 30 or a[3] */
/* A[i]  = *(A-i) */
```
NOTE  - a pointer can divide an array using a dynamic pointer

Double casting
```
int a[5] = {10,20,30,40,50};
double *q;
q = (double *)(a+3); /*to point to a[3]*/
printf("%d",*((int *)q)); /*to print value as int*/
```
Printing an array without using an index
```
int a[5] = {10,20,30,40,50};
int *p;
for(p=a ; p < a + 5 ; p++)
  printf("%d",*p);
```
Printing an array without using an index (array and pointer are different type}
```
int a[5] = {10,20,30,40,50};
double *p;
for(p=(double *)a ; p < (double*)(a + 5) ; ((int*)p)++)
  printf("%d",((int *)p));
```
in order to get the size of a static pointer (array) 
```
int a[5] = {10,20,30,40,50};
printf(sizeof(a)); /* would return the number of cells X (size of int) */
printf(sizeof(a) / sizeof(a[0])); /* prints 5*/
```

#### Dynamic Pointer

need to use  stdlib.h
1.  malloc (num_of_bytes)  - allocates #num of bytes, if successful returns  pointer of type void* (general pointer) else returns NULL.
NOTE - need to check allocation because might fail.
```
int *p;
p = (int*) malloc(4*sizeof(int));
if(!p){
   printf("memory allocation failed");
   exit(0);
}
....
free(p);
```
2.  calloc(num of units, size of 1 unit in bytes);
3. realloc(pointer, num_of_bytes) - reallocates in order to increase or decrease a pointers size.  it is best used with a helper pointer
```
int *p = (int *) malloc(4*sizeof(int)); 
int *q;
q = (int *) realloc(p,6*sizeof (int));
if(!q) {
  printf("memory allocation failed");
  exit(0);
}
p = q;
```
NOTE  a dynamic pointer defined inside a function, would not get auto released upon exit.

#### Matrix

Define

```	
	int m[3][2]={{10,20},{30,40},{50,60}};
	int *p;
	for (p=(int*)m;p<((int*)m)+6;p++)
	  printf("%d\n", *p); // would print entire array
```
Different ways to assign values
```
p[1][2] = 8;
*(p[1]+2) = 8;
(*(p+1))[2] = 8;
*(*(p+1)+2) = 8;
```

### Error type

**lvalue** - left value : indicates a value that can only be used to receive a value
**rvalue** - right value: indicates a value that can only be used for input for another value (example : the digit 5)

### pointer to function
```
int (*p)(int,int);
p = func; //* p is now pointing to a function*/

//calling the function using the porinter

(*p)(8,5) 
//or
p(8,5)
 
```

### string.h

* memcpy(string1,string2,num_byte) - copies from string2 to string1 x bytes.

#### struct

```
struct location{
int x;
int y;
char locName[20];
}

/*define*/
struct locatioin loc;
loc.x = 100;
loc.y = 120;
loc.locName = "nowhere"

/*method II to define*/

struct foo{
int x;
int y;
char c;
} firstVar,secVar; /* <-- */

/* method II.2 if no name used after struct so can only be used by variables after it*/

struct{ 
int x;
int y;
char c;
} firstVar,secVar;

```

####typedef
define a new variable type.

```
typedef struct{
  int x;
  int y;
  char c;
  } location;  /* can now 'location' instead without 'struct'*/

location loc;

/* to define an array*/

typedef int image[256] [256];
image pic;
```
### Linked list

```
/*define a linked list*/


typedef struct node *ptr; /* */
typedef struct node{
  int data;
  struct node* next; /* can instead write ptr in type */
 } item;

/* accessing a field */
ptr pt;
(*pt).data = 8;
/* OR */
pt->data = 8;

/* add a new item */
ptr ptrData;
ptr p1,p2;
ptr t;
t = (ptr) malloc(sizeof(item));
if (!t) /* not NULL */
  { 
    printf("\n cannot allocate memory for list \n");
    exit(0);
   }
 
t->data = n; /* n is a new number */

p1= *ptrData;
while ((p))
  {
    p2 = p1;
    p1 = p1 -> next;
   }
```

###Operate program from cmd
* argc - the number of arguments (including programs name)
* 

``` 
int main(int argc ,*argv [] );

```
### Multiple variable

* va_list  _name_ -   declaration of pointer to arguments 
* va_start (name,lastarg) - initialization of argument pointer,  _lastarg_ is last named parameter of the function
* va_arg(name,type) - access next unamed arg, update pointer
* va_end(name) - call before exiting function
```
/*EXAMPLE : print the number of even number*/
# include <stdio.h>
# include <stdlib.h>
int f(int x,...);
int main ()
{
  printf("\n %d \n",f(10,20,30,40,-99));
}

int f(int x,...)
{
  va_list p;
  int cnt = 0;
  int num;
  int i;
  va_start(p,x);

  while (num !=99)
  {
    cnt+= (num%2)?0:1;
    num = va_arg(p,int);
  }
  va_end(p);
  return cnt;
}/*f*/
```
### Boolean true/fals
. In C _**true**_ is represented by any numeric value not equal to 0 and _**false**_ is represented by 0
 
###Working with files

Steps:

1. Opening a file- need to check for errors.
2. Using data from file.
3. Closing the file
* fopen ("FILENEMAE",r/w/a); 
	* r- read only.
	* w - write
	* a - append (update)
**Binary** - add 'b' after letter to open as a binary file
**Text** - add 't' for text file.


| Action | File exists |File not exists|
|--------|----------|---------------|  
| r | opens file,points to start | return null |
| w | opens file,deletes content,points to start| creates new file points to start |
| a | opens file ,points to end, keeps existing data | creates new file points to start |
| r+ | same as 'r' only with write | same as 'r' | 
| w+ | same as 'w' only with read | same as 'w' |
| a+ | same as 'a' only with read&write | same as 'a'|

* rewind (filePointer) - returns the pointer to the start of the file.
* fgetpos (filePointer, & **fpos_t** pointer) - copies current pointer position in pointer1 to pointer2.
* fsetpos  (filePointer, & **fpos_t** pointer) - sets position.
* ftell (filePointer) - size of file till filePointer.
* fseek(filePointer, NumOfBytes ,SEEK_SET/CHR/END) - go X bytes from ,return non zero if out of bounds.
SEEK_SET - start of file
SEEK_CHR - current possition
SEEK_END - end of file

* fgets(buf, int, filePointer) - read char till -
	* enter 
	* EOF
	* int number of char.
* fgetc(
* fprintf - prints the chareter 
* function size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *stream) writes data from the array pointed to, by ptr to the given stream. - prints state of memory
* fread- returns how many units a red.

#### Default open files

 - **stdin** - standard  input file (keyboard)  
 - **stdout** - standard output file(screen)
 - **stderr** -  standard error  file(screen)

#### Macro
* Can't be recursive 
* Doesn't return a value 
* Faster then a function
* When defining a variable - need to open a block  **{  }**
* Just copies the code so need to place " __\ __ " to start new line

```
#define add(x,y) x+y
#define mul1(x,y) x*y;
#define mul2(x,y) (x)*(y);
int main()
{
  int z = 50;
  int a,b,c;
  a= add(5,8);  // get ->  a = 5 + 8
  b = mul1(3+5,10+2); // get -> 3 + 5 * 10 + 2
  c = mul2(3+5,10+2); // get -> (3 + 5) * (10 + 2)
  d = mul2(add(3,5),add(10,2); // get -> (3 + 5) * (10 + 2)
                   
```
* use # in order to place a variable as a string
* use ## to join
```
# a // "a"
a##20 // result "a20"
```
Predefined Macros in C language
Predefined macro	Value
_______DATE_______	String containing the current date
_______FILE_______	String containing the file name
_______LINE_______	Integer representing the current line number
_______STDC_______	If follows ANSI standard C, then value is a nonzero integer
_______TIME_______	String containing the current date.


###union 

* can define a multi purpose variable 
```
union u{
  int x;
  char y;
  double z;
} A[4];

A[0].x = 7; // saves values as an int
a[1] .y = 'a' // saves value as a char
```

###bitplay

* can receive only 0 or 1.
```
struct exm{  // the entire size is 8 bits
 unsigned int a : 3 ;
 unsigned int b : 2 ;  
 unsigned int c : 1 ;
 unsigned int   : 1 ;  // no access to bits
} s1;
struct exm2{  // the entire size is 8 bits
 unsigned int a : 3 ;
 unsigned int   : 0 ;  // to start the new var in a new int
 unsigned int b : 2 ;
 // the complier would still create the remaining bits.

s1.a = 6  // sets three bits to 110
```
#### Genral knowlage

* GUI 
	* X Windows Systems (basic)
	* GNOME
	* KDE
Main memory is divided up into cache line
When the program needs to read a memory word, the cache hardware checks to see
if the line needed is in the cache. If it is, called a cache hit
#### Process IDs & process groups

A process has its own, unique process ID
```
pid_t getpid();
```
A process belongs to exactly one process group
```
pid_t getpgrp();
```
A new process belongs to which process group?
Its parent’s process group

A process can make a process group for itself and its children
```
pid_t pid = getpid();
setpgid(0, 0);
getpgrp()
```
#### Create a new process

* int fork(void)
	* Create a new process that is identical to the parent process
	* Return 0 to child process
	* Return child’s pid to the parent process
	* Call once, return twice
```
#include <unistd.h>
#include <stdio.h>

int cnt = 0;

int main(void)
{
  if (fork() == 0){
    cnt ++;
    fork();
    cnt++;
  }
  cnt ++;
  printf("%d", cnt);
  return 0;
  
}
```
> Possible output:
133
313
331


#### Reaping child process
* Child process becomes zombie when terminates
	* Still consume system resources
	* Parent performs reaping on terminated child
~~~
pid_t wait(int *status)
pid_t waitpid(pid_t pid, int *status, int options)
~~~
* Straightforward for reaping a single child
* Tricky for Shell implementation!
	* Multiple child processes
	* Both foreground and background
```
int main(){
  int status;
  int counter = 1;
  if (fork() == 0){
    counter ++;
    printf("%d", counter);
  }else {
    if (fork() == 0){
      printf("9");
      counter --;
      printf("%d", counter);
      exit(0);
    }else {
      if (wait(&status) > 0){
        printf("6");
      }
    }
  }
  printf("8");
  exit(0);
}
```
>Answers:
A. Y
B. N
C. Y
D. N
E. Y

```
for (i=0; (i < N_CPU) && (pid = fork());i++)
```

exit() -
* Terminates the calling process immediately. 
* Any open file descriptors belonging to the process are closed 
* Any children of the process are inherited by process 1, init, and the process parent is sent a SIGCHLD signal.
* Releases malloc

איך ניתן לחכות לבן כלשהו
``
waitpid (-1, &status, 0)
``

NO_HANG - makes it so waitpid continues even if there are no sons.

wait() - waits for only ONE son.

To gather all the son till they end
```
while(-1 !=wait ()) 
```
This is not good way.  if there are no sons then there would be a system error (-1)

when using fork() the file location remains the same in all sons

argv[0]   -  The name of the file 

#### exec  

* calls for a new program
* The pid is the same
* Once ruining, the program overruns exciting binaries and the program gets a new memory allocation. 


**System() call  can fail**

```
system()  
```

Is equal to 
```
fork ()
exit()
```

#### For the test

Chapter 
* X 1.1 What is an operating system
* X 1.2 History of operating systems  
	* The differences between Gen II  to Gen III
* X 1.3  The operating system zoo
* X 1.4 Computer hardware review
	* Only Chapter 5  - I/O
* V 1.5 Operating system concepts
	* Slides 17, 24
* V 1.6 System calls
* V 1.7 Operating system structure

What is a Operation system?
* Used as the go-between users/software to hardware,

	* How -
		* interpreter -  Reads a line and executes it. 
	* The OS hides the hardware
	*  Resource handling
	* process handling
	* Schecdualr 
	* Permissions
	* Hi
	 
API -> uses to call system call.
The  API is a virtual system to talk to hardware.

* It is an extended machine
	* Hides the messy details which must be performed
	* Presents user with a virtual machine, easier to use
* It is a resource manager
	* Each program gets time with the resource
	* Each program gets space on the resource

כל ניסיון להגן ללא תמיכת בחומרה לא יהיה לא רלוונטי


* The processor has two states (PSW)
	* User mode 
	* Kernal mode 
* Once a program wants to run the Bit for User mode is lit to restrict it from accesing kernal fetures. 


PC (program counter)  - מונה הפקודות מצביע על הפקודה הבא לביצוע

Can we change from user to karnel?
No 
If we try to run a karnel code with a user mode ?  you would get an error intrropt.

פיסקות חומרה הן א-סינכורניות 

System calls process management

```
pid = fork() // create a child process identical to the parent
pid = waitpid(pid, &statloc, option) // wait for chiled to terminate
s = execve ( name, argv, environp) // replace a process core image
exit(status) // Terminate process execution and return status
getppid()  // Get parent  process's ID
getpid()  // Get process's ID
```

### System calls file management (need to know for test)
```
fd = open(file, how,...) // Open a file for read and/or write
s= cloe(fd) // close an open file
n = read(fd, buffer, nbytes) // read data from a file into a buffer
position = lseek(fd, offset, whence) // Move the file pointer
s = stat(name, &buf) // Get a file's status information

```

System calls directory management
```
s = mkdir (name, mode)  // create a new directory
s= rmdir(name)// 
s= link(name1, name2) // create a new entry, name2, pointing to name1
s= unlink(name) // Remove a directory entry
s= mount(special, name, flag) // mount a file system
s= umount(special) // unmount a file system
```

System calls for misc tasks
```
s= chdir(dirname) // Change the working directory
s= chmod(name, mode) // Change a file's protection bits
s = kill(pid, signal) // sned a signal to a process
seconds = time(&seconds) // Get the elapsed time since Jam 1 , 1970
```
Microkernal - קל לבזר, לעדכן להרחיב, 

חסרונות - המון טרפיק לקרנל כל פעולה חייב לעבור דרך מיקרוקרנל

ditrbuted system
ממוקם במחרק פיזי שונה, הפרדה בין השירותים השונים

client server model - disadvantage - large overhead between different component

OS architecture - with with defense of kernal mode / user mode -
* Monolitic strucure
* Client-server structure
* Ring structure  

All services of VM machine can be implemented in an extended machine

 Minimal Kernel is feature of Client-server OS model

TRAP 
מעבירה את מערכת ההפעלה ממצב משתמש (יוזר) למצב ראשוני (קרנל) בעקבות קריאה מתוכננת של המשתמש ל - סיסטם קול . פסיקת חומרה מעבירה את מערכת ההפעלה ממצב משתמש למצב ראוני בעקבו אירוע אסינכורני כלשהו 

#### chapter 2

2.1 processes
2.2 therads
2.3 interprocess communication - mmn11
2.4 Classical IPC problems
2.5 Scheduling
2.6 Freezing

ניצולת מיטבית במעבדים סוג 2
quantom = infinte 

### Critical Regions (1)

#### Four conditions to provide mutual exclusion
|# | Condition | Solution |
| - | -  | - |
|1| No two processes simultaneously in critical region | Simple|
2 |  No assumptions made about speeds or numbers of CPUs| Full (2-4) |
3| No process running outside its critical region may block another process | Full (with 2-4)|
| 4 | No process must wait forever to enter its critical region | Full (with 2-4) **|

** ניתן להניח שכל משאב בבחינה מקיים את תנאי 4 בגלל שכולם מקיימים : 
בקשת משאב
תפיסת משאב
שיוך משאב
שחרור משאב

### part 2.3

#### Mutual Exclusion with sleep and Busy Wating
##### Disabling interrupts  -  
 אסור לתת למשתמש כזה כח, אם יישכח להחזרת את הפיסקות אז המחשב נתקע, מערכת ההפעלה משמתמש בטריק זה של ביטול פסיקות לזמן קצר מאוד.
 ** לא עובד על מספר מעבדים **
 
##### Lock variables

* V Strict alternation
* V Peterson's solution
* V The TSL instruction
צורך משאבים

#### Mutual Exclusion with Sleep and Wakeup
יש סכנת קיפאון
Semaphores & Mutexes
Monitors 
Message Passing

#### Semaphores
A type of flag

Mutexes


Moinitor
41
לוודא שרק אחד מחזיק את המוניטור

signal.h


set jump.h
Saves current status 


Mintors

message passing
סינכרון הודעות במערכות מבוזרות


|Recipe| Cups of Flour| Cups of Sugar|Eggs| Cups of Milk|Cups of Butter| |-|-|-|-|-| |Cupcakes|…|…|…|…|…| |Pancake|…|…|…|…|…| |Cookie|…|…|…|…|…| |Bread|…|…|…|…|…|


> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1NTgzMTYyMl19
-->