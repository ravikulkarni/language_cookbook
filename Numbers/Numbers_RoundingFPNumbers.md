#Rounding floating type numbers

## Java

This can be done using class DecimalFormat class. The

```java
double d = 1.23456;
DecimalFormat fmt =new DecimalFormat(“#.##”);
double val = Double.valueOf(fmt.format(d));
```

Listing all format patterns is beyond the scope of the book. But please refer to the javadoc for DecimalFormat class to know the patterns.

## Perl
This can be done using sprintf function.
```perl
my $no1 = sprintf(“%.3f”, 3.14236);   # $no1 is now 3.142
```
In addition to %f specifier there are %e (for floating point in scientific notation) and %g (for either floating or scientific notation)

## C
This can be done using sprintf and atof. The sprintf function rounds the floating point to the desired precision and then atof function call converts string to float.

```c
char buffer[256];
float val = 1.234567f;
sprintf (buffer,"%.1f\n", val);
float rValue = atof(buffer);
```

## Bash

This can be done using print statement and then assigning it to variable as shown below

```bash
roundedNo=$( printf "%0.2f\n" 3.1423456 )
```

The result is 3.14.
