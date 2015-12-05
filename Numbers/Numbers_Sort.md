# Sorting numbers

## Java

Sorting numbers in java is a very easily done using Collections classes

```java
int arr[] = {9,5,7,8,4};
Arrays.sort(arr);
```
Just like for int, there are functions for the other data types like byte, short, double, long data type.

## Perl

Sorting numbers can be done using <=>   operator and sort function

Example is given below

```perl
@sorted = sort { $a <=> $b } @unsorted;
```

## C

There is a function readily available in C stdlib named qsort. This function does quick sorting. The qsort takes a function pointer as an argument which it uses to sort. The implementation of the function can be customized to return the value after comparison. Below is the example of how it could be used to sort strings.

```c
int compare (const void *a, const void *b) {
  const int **ia = (const int **)a;
  const int **ib = (const int **)b;
  return *ia - *ib;
}

void sort()
{
  int *arr[] = { 7,5,6,9};
  size_t arrLength = sizeof(arr) / sizeof(int *);

  /* sort array using qsort functions */
  qsort(arr, arrLength, sizeof(int *), compare);
 //The arr will have now sorted array.

}
```

## Bash
Array can be sorted in following way.
Here intArr is an array of numbers. The array is first printed out, then space is replaced with a new line and then piped onto sort function with -n as parameter to tell sort function that the sorting has to be done for numbers

```bash
intArr=( 4 6 3 10 2 )
sortedArr=( $( echo ${intArr[@]} | sed 's/ /\n/g' | sort -n ) )
```

The sortedArray has the numbers sorted numerically.



