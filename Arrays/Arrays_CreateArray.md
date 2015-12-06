# Defining/creating arrays

## Java
In java the arrays are defined as below
```java
int []a = new int[2];
a[0] = 0;
a[1] = 1;
```

Or to initialize them,

```java
int []a = {1,2};
```

An example for multi dimensional array initialization is below

```java
int[][] twoDimArray = { {1, 2, 3},
                         {4, 5, 6},
                         {7, 8, 9}
						};

String []strArray = new String[10];
```

In the above example, you could replace int with any other class or primitive data types to create an array

The above method of declaration of array is not a collection to which elements can be added or removed. With the method given above, once the array size is set then it cannot be changed. To create an array as a collection, use the ArrayList or Vector class from java.util package. All the examples below uses ArrayList class but the methods supported by ArrayList class are same as the ones in Vector class. Example is given below

```java
List strList = new ArrayList();
strList.add("Element1");
strList.add("Element2");
```

Or List that holds Integer is defined as

```java
List intList = new ArrayList();
intList.add(new Integer(1));
intList.add(new Integer(2));
```

The initial capacity can be mentioned in the constructor of ArrayList. For example if you want to have an integer arraylist with 10 items you could say.

```java
List intList = new ArrayList(10);
```

## Perl
Array are defined as below

```perl
my @arr = (‘one', 'two', 'three');
my @numArr = (1..10);
```

A 2 dimensional array can be defined as below

```perl
my @row1 = qw(1 2 3 4 5);
my @row2 = qw(11 12 13 14 15);
my @array_2d = (\@row1, \@row2);
```

## C
In C when you define an array, the memory is reseved for its elements. Below are the methods to define/initialize the array in C

```c
int oneDimArray [5];
int anotherOneDimArray[5] = {1,2,3,4,5};
int twoDimArray [3][3];
int twoDimArray1[3][3] = {
{1,2,3},
{4,5,6}
{7,8,9}
};
```

## Bash
Array elements may be initialized with the variable[xx] notation. Alternatively, a script may introduce the entire array by an explicit “declare -a variable statement”. To dereference (retrieve the contents of) an array element, use curly bracket notation, that is, ${element[xx]}.

For example

```bash
array1[2]=20
```

The above element is accessed as below

```bash
${array[2]}
```

The index need not be continous here.
