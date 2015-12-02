# Sorting strings

## Java

If the strings are to be sorted with natural order, it can be easily done using class from util package

```java
String arr [] = {“abc”, “xyz”,“lmn”};
java.util.Arrays.sort(arr);
```

To do Locale aware sorting you need to use Collator class. Below is an example

```java
  	Collator fr_FRCollator = Collator.getInstance(new Locale("fr","FR"));
  	 String eWithCircumflex = new String("\u00EA");
  	 String eWithAcute = new String("\u00E9");

  	 String peachfr = "p" + eWithAcute + "ch" + eWithAcute;
  	 String sinfr = "p" + eWithCircumflex + "che";

  	 String [] words = {
  	 	peachfr,
  	 	sinfr,
  	 	"peach",
  	 	"sin"
  	 };
  	 List list = Arrays.asList(words);
  	 Collections.sort(list, fr_FRCollator);
```

## Perl

For numerical sort
```perl
@sorted = sort { $a <=> $b } @unsorted;   
```

For ascii based sorting
```perl
@sorted = sort { $a cmp $b } @unsorted ;  
```
For alphabetical sort
```perl
@sorted = sort { lc($a) cmp lc($b) } @unsorted;
```
Where the 
``` cmp and <=> ``` 
return the following

```
1  if $a greater than $b
0  if $a equal to $b
-1 if $a less than $b
```

@unsorted array is the array which is to be sorted and @sorted array is the one which is sorted.

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

Array can be sorted in following way.
Here strArr is an array of chars. The array is first printed out, then space is replaced with a new line and then piped onto sort function

```bash
strArr=( zero one two three four )
sortedArray=( $( echo ${strArr[@]} | sed 's/ /\n/g' | sort  ) )
```

The sortedArray has the words sorted. Here first the array is printed out, piped to sed whose pattern replaces spaces with new line. Then the output of that is piped to sort function. This will sort the strings. The output of the whole expression is included as a list.



