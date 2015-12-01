# Reverse string

## Java

This can be done using StringBuffer class and using reverse function from it.

```java
String str = “Today is bright sunny day”;
String reverseStr = new StringBuffer(str).reverse().toString();
```

The above code first creates StringBuffer object from String object. Then calls method reverse() which returns a StringBuffer object. Then from StringBuffer object, toString method is used to convert StringBuffer to String.

## Perl
This is done using function “reverse” in scalar context

```perl
my $str = “Today is bright sunny day”;
my $reverseStr = reverse( $str );
```

## C
There is no ready made function available to reverse the string in C. An implementation below is one of the way to reverse the string.
The string can be reversed by using xor operations on character. To see how xor works follow the table below where each row of the table corresponds to each of the xor operation in the while loop.


|              | c1 (ASCII A) | c2 (ASCII Z) | New c1            | New c2            |
|--------------|--------------|--------------|-------------------|-------------------|
| c1 = c1 ^ c2 | 1000001      | 1011010      | 0011011           |                   |
| c2 = c2 ^ c1 | 0011011      | 1011010      |                   | 1000001 (ASCII A) |
| c1 = c1 ^ c2 | 0011011      | 1000001      | 1011010 (ASCII Z) |                   |


As can be seen above the c1 and c2 started out with A and Z respectively. After the three XOR operations c1 became Z and c2 became A.

```c
char* reverse(char* str) {
 int end= strlen(str)-1;
 int start = 0;

 while( start<end )  {
   str[start] = str[start] ^ str[end];
   str[end] =  str[end] ^ str[start];
   str[start] = str[start] ^ str[end];

   ++start;
   --end;
 }

 return str;
}
```

## Bash

In bash this can be done by using a combination of

```bash
-${string%substring} :Deletes shortest match of $substring from back of $string
${#string} : Length of $string
${string:position:length} : Extracts $length characters of substring from $string at $position.

stringA = “Today is bright sunny day”
len=${#stringA}
revStr=""
for (( i=$len ; i>0 ; i-- ))
do
   revStr=$revStr""${stringA:$i-1:$i}
   stringA=${stringA%${stringA:$i-1:$i}}
done
```


