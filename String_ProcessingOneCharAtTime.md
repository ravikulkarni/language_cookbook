# Processing string one character at a time

## Java

The simplest way to do this is using function toCharArray of String function

```java
String str = “Processing string”;
char chars[] = str.toCharArray();
```

Then the chars array can be iterated over to process characters one by one.

## Perl

There are 2 ways to do this

#### Option 1

```perl
my $str = “Processing string”;
my @chars = split(//,$str);  # @chars will have each element as character from the $str
```

This will put all the characters into an array. Then each element array can then be processed using for loop

#### Option 2

```perl
while($str =~ /(.)/g) {
	#Here $1 is the character
	#Code to process something the characters.
}
```

## C

In C the character string is represented as a character array. Accessing each character of a string is simply accessing array elements.

```c
char* str = “Processing characters in string”;
int len = strlen(str);
int i=0;
for(i=0;i<len;i++) {
  //Process each character str[i];
}
```

## Bash

Example below is one way to process characters of a string.

```bash
stringA = “Processing characters in string”
len = ${#stringA}
for((i=0; i<$len; i++))
do
   ch = ${stringA:i:1}
done
```
