# Printing string with formatting control

The print functions in all of the 4 languages below are powerful functions and take arguments in different combination to output formatted strings. Listing all the combination of the arguments is beyond the scope of this book. Please refer to detailed documentation for additional details. Few examples are given below

## Java

This can be done in using format method of PrintStream. The format string syntax is given in java.util.Formatter class. Listing all the options here is beyond the scope of the book but below are some examples

```java
int i = 2;
double r = Math.sqrt(i);
System.out.format("The square root of %d is %f.%n.", i, r);  // The value printed out is “The square root of 2 is 1.414214.”
```

## Perl

This can be done using “printf” function. The printf function is a very powerful function that lets you format in practically any form. Please refer to references to get detailed information on the sprintf

Below are some of the examples

```perl
printf ("Characters: %c \n",65); // Prints "Characters: A"
printf ("Decimals: %d \n", 1); // Prints "Decimals: 1"
printf ("Preceding with blanks: %3d \n", 1); //Prints "Preceding with blanks:   1"
printf ("Preceding with zeros: %03d \n", 1); //Prints "Preceding with zeros: 001"
printf ("Some different radixes: %d %x %o %#x %#o \n", 100, 100, 100, 100, 100);//Prints "Some different radixes: 100 64 144 0x64 0144"
printf ("floats: %4.2f %+.0e %E \n", 3.1416, 3.1416, 3.1416); //Prints floats: 3.14 +3e+000 3.141600E+000
printf ("%s \n", "A string"); Prints "A string"
```

## C

There is also a printf function which takes different arguments to indicate the formatting to be printed out.
.  Please refer to references to get detailed information on the sprintf.

```c
printf ("Characters: %c \n",65); // Prints "Characters: A"
printf ("Decimals: %d \n", 1); // Prints "Decimals: 1"
printf ("Preceding with blanks: %3d \n", 1); //Prints "Preceding with blanks:   1"
printf ("Preceding with zeros: %03d \n", 1); //Prints "Preceding with zeros: 001"
printf ("Some different radixes: %d %x %o %#x %#o \n", 100, 100, 100, 100, 100);//Prints "Some different radixes: 100 64 144 0x64 0144"
printf ("floats: %4.2f %+.0e %E \n", 3.1416, 3.1416, 3.1416); //Prints floats: 3.14 +3e+000 3.141600E+000
printf ("%s \n", "A string"); Prints "A string"
```

## Bash

Just like other language, there is a printf with formatting control in it. Below are some examples.

```bash
printf "Decimals: %d \n" 1 #Prints "Decimals: 1"
printf "Preceding with blanks: %3d \n" 1 #Prints "Preceding with blanks:   1"
printf "Preceding with zeros: %03d \n" 1 #//Prints "Preceding with zeros: 001"
printf "Some different radixes: %d %x %o %#x %#o \n" 100 100 100 100 100 #Prints "Some different radixes: 100 64 144 0x64 0144"
printf "floats: %4.2f %+.0e %E \n" 3.1416 3.1416 3.1416 #Prints floats: 3.14 +3e+000 3.141600E+000
printf "%s \n" "A string" #Prints "A string"
```
