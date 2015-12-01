# Accessing Substrings
## Java
The way to do this is using function substring from String class. From javadoc, following are the overloaded substring methods.
```java
String     substring(int beginIndex)
String     substring(int beginIndex, int endIndex)
```

These methods return a new string that is a substring of this string. The beginning index, inclusive and the endIndex is exclusive. Throws IndexOutOfBoundsException - if the beginIndex is negative, or endIndex is larger than the length of this String object, or beginIndex is larger than endIndex.

Below are some examples of using those.

```java
String str = “Today is a bright sunny day”;
String day = str.substring(0,5);  //Returns “Today”
String weather = str.substring(11);  //Returns “bright sunny day”
```

## Perl

The way to do this in perl using substr function. From the Perl documents, following are substr function which takes different parameters.

```perl
substr EXPR,OFFSET,LENGTH,REPLACEMENT
substr EXPR,OFFSET,LENGTH
substr EXPR,OFFSET
```

Extracts a substring out of EXPR and returns it.
First character is at offset 0 . If OFFSET is negative, starts that far back from the end of the string.
If LENGTH is omitted, returns everything through the end of the string.
If LENGTH is negative, leaves that many characters off the end of the string.

```perl
my $str = “Today is a bright sunny day”;
my $day = substr ($str, 0,5);     #Returns “Today”
my $weather = substr ($str, 11);  #Returns “bright sunny day”
my $s1 = substr ($str, -3); #Returns “day”
my $s2 = substr ($str, -9,5); #Returns “sunny”
```

## C

In C this is done using strndup function. There is a use of pointers here. The example below creates a duplicate string and returns it. The strndup() function returns a pointer to a new string which is a duplicate of the string s and is n characters long. Memory for the new string is obtained with malloc, and can be freed with free. If s is longer than n, only n characters are copied, and a terminating null byte ('\0') is added.

```c
char* substring(int startIndex, int endIndex, char * str) {
  return strndup((str + startIndex), (endIndex-startIndex));
}
```

This function can be called by deriving end index using different functions as given in string.h header file. strlen is one of the functions that can be used to derive the two indices from one of the index.


## Bash

This can be done in bash using either ${string:position} or  ${string:position:length}

```bash
stringA = Today is a bright sunny day
echo ${stringA:6}   //Returns “is a bright sunny day”
echo ${stringA:6:2} // returns “is”
```
