# Deleting element from array.

## Java

In Java for the arrays defined with new operator, there is no way to delete the element. An element can be set to a new value or null.

In Java for ArrayList class, there are methods to remove objects from the ArrayList. They are as below

```boolean remove(Object o)```
   Removes the first occurrence of the specified element from this list, if it is present.
```boolean removeAll(Collection<?> c)```
   Removes from this list all of its elements that are contained in the specified collection.
```protected void removeRange(int fromIndex, int toIndex)```
   Removes from this list all of the elements whose index is between fromIndex, inclusive, and toIndex, exclusive.

In the strList ArrayList object defined, examples below show how to remove the elements

```java
ArrayList strList = new ArrayList();
strList.add(“String1”);
strList.add(“String2”);
strList.add(“String3”);
strList.add(“String4”);
strList.add(“String5”);
strList.remove(“String1”);
```

After above operations on strList, it will contain only ```“String2”,“String3”,“String4”,“String5”```

## Perl
In Perl there is a delete function to the delete the elements of array. Below are some examples

```perl
my @array = (0,1,2,3,4,5,6);
# delete a range
delete @array[0..3];
# or a discontiquous slice
delete @array[0,3,5];
```

There are also functions to remove first and last elements in array. These functions are as below

```
pop() - removes the last element of an array.
shift() - removes the first element of an array.
```

Example is given below

```perl
my @arr = ('zero', 'one', 'two', 'three','four');

pop(@arr); # @arr now contains ('zero, 'one', 'two', 'three')
shift(@arr); # @arr now contains ('one', 'two', 'three')
```

## C
In C there is no way to delete the elements from array. You can overwrite the element to indicate that it is deleted. But you cannot really remove the element from array.

## Bash
In Bash the element can be deleted using ```unset``` call

```bash
declare -a array1=(1,2,3,4)
unset array1[0]
```
