# Adding element to array

## Java
There is no way to add elements into array defined by “new” operator. The array size is fixed when defined that way. However you can set the values of the array element. Example below shows how to do that for the arrays defined in previous section

```java
int []a = new int[2];
a[0] = 0;
a[1] = 1;
a[0] = 1;
a[1] = 2;

String []strArray = new String[10];
strArray[0] = “string1”;
strArray[1] = “string2”;
```

For the ArrayList there are methods to add the data. Below is information on those methods

```boolean add(E e)```
  Appends the specified element to the end of this list.
```void add(int index, E element)```
  Inserts the specified element at the specified position in this list.
```boolean addAll(Collection<? extends E> c)```
  Appends all of the elements in the specified collection to the end of this list, in the order that they are returned by the specified collection's Iterator.
```boolean addAll(int index, Collection<? extends E> c)```
  Inserts all of the elements in the specified collection into this list, starting at the specified position.

For example to add some strings to strList ArrayList object defined above

```java
List strList = new ArrayList();
strList.add(“String1”);
strList.add(“String2”);
strList.add(“String3”);
strList.add(“String4”);
strList.add(“String5”);
strList.add(1, “String21”);   //Changes String2 added above to String21
```

## Perl

In Perl there are 4 functions to add and remove the elements from array

```perl
push() - adds an element to the end of an array.
unshift() - adds an element to the beginning of an array.
```

Example of this is given below

```perl
my @arr = ('one', 'two', 'three');
push (@arr, 'four'); # @arr now contains ('one', 'two', 'three','four')
unshift (@arr, 'zero'); # @arr now contains ('zero', 'one', 'two', 'three','four')

pop(@arr); # @arr now contains ('zero, 'one', 'two', 'three')
shift(@arr); # @arr now contains ('one', 'two', 'three')
```

## C
In C there is no way to increase the size of array once it is declared.
However you can change the elements of array. In example below you cannot change the length of array. However you can change the element values

```c
int a1[10];
a1[0] = 1;
a1[0] = 2;
```

If the array is initialized using malloc function, then it can be resized to add more elements.
For example

```c
int *a1 = malloc(2);
a1[0] = 1;
a1[1] = 2;
int count = 4;
a1 = (int*) realloc (a1, count * sizeof(int));
a1[0] = 4;
a1[1] = 3;
a1[2] = 2;
a1[3] = 1;
```
where count is the new size and a2 is the new size

## Bash
In Bash, you can just add element to arry. There are no restriction on indices. For example if there is an array with 2 elements you can just add another element by incrementing the index.
Example is below

```bash
a1[0]=zero
a1[1]=one
a1[2]=two  #Newly added element.
```

Another example below states how to add the element to array.

```bash
a1=( ${a1[@]} three )
# or
a1[${#a1[*]}]=four
```
