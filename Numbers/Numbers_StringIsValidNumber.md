# Checking whether a string is a valid number

## Java

This can be done using parseInt function and checking for the NumberFormatException . If the string is not a number then the exception is thrown

```java
String str = “124”;
try {
int intStr = Integer.parseInt(str);
} catch (NumberFormatException e) {
	// The String is not number
}
//The string is a number.
```

## Perl

This can be done using regex.

```perl
my $str = “124”;
if ($str =~ /^([+-]?)(?=\d|\.\d)\d*(\.\d)?([Ee]([+-]?\d+)+)?$/) {
    # $string is a number
} else {
    # $string is not and number
}
```

## C

A string can be checked if it is a number by checking each of the character for digit using isdigit() function call. The first character can be either + or -

```c
An example below illustrates this.
 char str[]="-1996";
 if((str[0] != '+') && (str[0] != '-')) {
	notNumber = 1;
 }
 int i;
 for(i=1;i<strlen(str);i++) {
	if (!isdigit(*str[i])) {
 	notNumber = 1;
	}
 }
 if(notNumber) {
	printf("The string is not a number\n");
 } else {
	printf("The string is a number\n");
 }
```

## Bash

An example below shows how a string can be checked if it is a valid number. The regular expression here checks for optional - sign in the beginning, with digits, followed by optional dot and digits 

```bash
if [[ $string =~ ^-?[0-9]+.?[0-9]*$ ]]
then
    	echo "String is a valid integer."
else
    	echo "String is not a valid integer."
fi
```
