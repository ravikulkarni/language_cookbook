# Converting between characters and values

##Java

### Converting Strings/Characters to number

Each wrapper class for the datatype has a parse function that takes String as an argument and returns corresponding data type number

```java
byte b = Byte.parseByte("123");
short s = Short.parseShort("123");
int i = Integer.parseInt("123");
long l = Long.parseLong("123");
float f = Float.parseFloat("123.4");
double d = Double.parseDouble("123.4e10");
```

Below is the code to convert character into corresponding int

```java
char c1 = ‘A’;
int c1int = c1;  //This will set c1int to 65.
```

Similarly a numeric value can be converted into char using casting

```java
char c = (char) 65;
```

## Perl

### Converting character to a number

This is done by using function “ord”

```perl
ord EXPR
ord
```
Returns the numeric (the native 8-bit encoding, like ASCII or EBCDIC, or Unicode) value of the first character of EXPR. If EXPR is an empty string, returns 0. If EXPR is omitted, uses $_ .

For example
```perl
my $no = ord('A');  #$no is 65
```

### Converting number to character

This is done by using function “chr”

```perl
chr NUMBER
chr
```
Returns the character represented by that NUMBER in the character set. For example, chr(65) is "A" in either ASCII or Unicode.
For example
```perl
my $c1 = chr(65);  #$c1 is A
```

## C

### Converting character to a number

The functions that can be used to convert from ascii string to integer or other data types are - atoi (to integer), atol (to long) , atof (to float).

```c
char * str = ‘123’;
int strInt = atoi(str); //strInt is 123.

char * str1 = ‘123.45’;
float strInt = atof(str); //strInt is 123.45
```

### Converting number to string.

This can be done using sprintf function as given below. sprintf is a very powerful function that takes in arguments in varios combination. Please refer to references to get additional details about sprintf. Explaining all the parameters of sprintf function is beyond the scope of this book.

```c
char strInt[10];
int a=10;

sprintf(strInt, “%d”, a);
sprintf(strInt,"%d",a) //converts to decimal base.
sprintf(strInt,"%x",a) //converts to hexadecimal base.
sprintf(strInt,"%o",a) //converts to octal base.
```

## Bash

In bash the variables are not typed. It means that dependent on the context, arithmetic operations can be on on them

For example

```bash
a=123
echo ${a/2/4/}   //Returns 143 - string operation
echo $(( a+2 )) // Returns 125 number arithmetic operation.
```
