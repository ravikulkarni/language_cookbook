# Appending one array to another
## Java

Below are the 2 ways of appending 2 arrays to one another..
First way is to create a new temporary array of size of both arrays and then copying

```java
int[] array1 = {0,1,2,3};
int[] array2 = {5,6,7,8,9};
int[] temp = new int[array1.length + array2.length];
System.arraycopy(array1, 0, temp, 0, array1.length);
System.arraycopy(array2, 0, temp, array1.length, array2.length);
array2 = temp;
```

## Perl
This is easily done using push function. Below is example

```perl
push (@array1, @array2);
```

## C

In C there are 2 ways to do this. One is to create third array and copy first 2 arrays into it. Another way is using ```realloc``` to change the size of one of the arrays and then adding the elements from other arrays to it.

## Bash

This is done in bash by simply passing 2 arrays as elements of the third array. This is shown in the example below

```bash
declare -a a1=( one two three )
declare -a a2=( four five six )

dest=( ${a1[@]} ${a2[@]} )
```
