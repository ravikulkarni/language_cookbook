# Sorting array

## Java
There is a method “sort’ provided in Arrays class that does the sorting. There are different methods that take array arguments of different types.

Examples is given below

```java
int [] array1 = {3,2,4,1,5};
Arrays.sort(array1);
```

## Perl
In Perl this can be easily done by using "sort" function
Below is an example

```perl
my @array = (6,0,3,2,1,5,4);
my @sortedArray = sort(@array);
```

## C

There is a function readily available in C stdlib named qsort. This function does quick sorting. The qsort takes a function pointer as an argument which it uses to sort. The implementation of the function can be customized to return the value after comparison. Below is the example of how it could be used to sort strings.

```c
int compare (const void *a, const void *b) {
  const char **ia = (const char **)a;
  const char **ib = (const char **)b;
  return strcmp(*ia, *ib);
}

void sort()
{
  char *str[] = { "abc", "lmn", "efg", "qrs"};
  size_t strLength = sizeof(str) / sizeof(char *);

  /* sort array using qsort functions */
  qsort(str, strLength, sizeof(char *), compare);
 //The str will have now sorted array.

}
```

## Bash

In Bash this is done by using a combination of sort , sed commands  as given below

```bash
intArr=( 4 6 3 10 2 3 )
sortedArr=( $( echo ${intArr[@]} | sed 's/ /\n/g' | sort -n ) )
echo ${sortedArr[@]}
```

Below is an example for string sorting

```bash
stringArr=( zero one two three four )
sortedArr=( $( echo ${stringArr[@]} | sed 's/ /\n/g' | sort ) )
echo ${sortedArr[@]}
```
