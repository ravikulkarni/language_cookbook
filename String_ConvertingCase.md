# Converting between upper case and lower case.

## Java

This can be done in for character or for a string. There are 2 methods viz toUpperCase and toLowerCase defined in class String and Character

```java
String str = “Today is a bright sunny day”;
String lowerCaseStr = str.toLowerCase();
String upperCaseStr = str.toUpperCase();
```

## Perl

This can be done using functions “uc”and “lc” or string escapes \L and \U
\l and \u can also be used to alter just first character where \l is for lowecase and \u is for uppercase.

```perl
my $str1 = “Today is a bright sunny day”;
print uc( $str1 ) ;   #Prints “TODAY IS A BRIGHT SUNNY DAY”
print “\U$str1” ;   #Prints “TODAY IS A BRIGHT SUNNY DAY”
print “\u$str1”; #Prints “Today is a bright sunny day”
print “\l$str1”; #Prints “today is a bright sunny day”
print lc( $str1 );  #Prints ”today is a bright sunny day”
print “\L$str1”;  #Prints ”today is a bright sunny day”
```

## C

The ctype.h header file has function defined to convert the character between uppercase and lowercase. The two functions to do these changes are toupper and tolower.

```c
 char *str = "Today is a bright sunny day";
 i=0;
 len = strlen(str);
 printf("%d: %s\n",len,str);
 char upperCaseStr[len + 1];
 for(i=0; i<len;i++) {
	upperCaseStr[i] = toupper(str[i]);
 }
 upperCaseStr[len] = '\0';
 ```
 
 For Lowercase conversion

```c
 char *str = "Today is a bright sunny day";
 i=0;
 len = strlen(str);
 printf("%d: %s\n",len,str);
 char lowerCaseStr[len + 1];
 for(i=0; i< strlen(str);i++) {
	lowerCaseStr[i] = tolower(str[i]);
 }
 lowerCaseStr[len] = '\0';
``` 

## Bash

The conversion is done using tr function

```bash
stringA = “Today is a bright sunny day”
l_str =`echo $stringA | tr A-Z a-z`  #  Makes str lowercase
u_str =`echo $stringA | tr a-z A-Z`  #  Makes str uppercase
```
