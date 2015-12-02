# Trimming blanks from ends of a string

## Java

This can be done using trim function of String class.

```java
String str = “   this string has leading and trailing spaces    “;
String trimmedStr = str.trim();
```

## Perl

The leading and trailing spaces can be removed by using substitution using regular expressions
In the example given below, ^\s+ means one or more leading spaces. \s+$ means one or more trailing spaces  .

```perl
my $str = “   this string has leading and trailing spaces    “;
$str =~ s/^\s+//;  #$str will be “this string has leading and trailing spaces    ”
$str =~ s/\s+$//;  #$str will be “this string has leading and trailing spaces”
```

## C

To detect if the character is a space, isspace is used. The way to trim these characters is to look for non space character from start and end, keep track of the position in a variable and then adjust the string accordingly adding a null termination character at the end of the adjusted string.

```c
char* removeSpaces(char* str) {
  int begin = 0;
  int end = strlen(str) - 1;
  //Get the location of first non space character
  while (isspace(str[begin])) {
     begin++;
  }
  //Get the location of non space character from end of the string
  while (isspace(str[end]) && (end >= begin)) {
     end--;
  }

  char *trimmedStr = (char *) malloc(end - begin + 1);
  // Adjust all the characters accordingly.
  int i;
  for (i = begin; i <= end; i++) {
	trimmedStr[i-begin] = str[i];
  }
  
  //Add Null terminating string
  trimmedStr[i - begin] = '\0';
  return trimmedStr;
}
```

## Bash

One of the easier way to do this is using sed as given below.

This will remove trailing spaces...

```bash
echo " line with leading and trailing spaces " | sed 's/ *$//g'
```
which results in
```
" line with leading and trailing spaces"
```

This will remove leading spaces...

```bash
echo " line with leading and trailing spaces " | sed 's/^ *//g'
```
which results in
````
"line with leading and trailing spaces "
```


