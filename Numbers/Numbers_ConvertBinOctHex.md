# Converting binary, octal and hexadecimal
## Java

This can be done using function parseInt into integer with second argument as radix to be used.
There are similar parse functions in each of the wrapper class short, byte, long

Similarly to convert an integer into string based on radix, toString function can be used.
There is also a function toString (which takes radix as an argument) in wrapper class for long data types.

```java
int i = 1023;

// Parse and format to binary
i = Integer.parseInt("1111111111", 2); // Parses binary into decimal 1023
String s = Integer.toString(i, 2);     // Converts decimal back to binary formatted string 1111111111

// Parse and format to octal
i = Integer.parseInt("1777", 8);       // Parses octal to decimal 1023
s = Integer.toString(i, 8);            // Converts decimal back to octal formatted string 1777

// Parse and format to decimal
i = Integer.parseInt("1023");          // Parse decimal 1023
s = Integer.toString(i);               // Converts into decimal format 1023

// Parse and format to hexadecimal
i = Integer.parseInt("3ff", 16);       // Parse hexadecimal into decimal 1023
s = Integer.toString(i, 16);           // Convert decimal into hex formatted string 3ff

// Parse and format to arbitrary radix <= Character.MAX_RADIX
int radix = 32;
i = Integer.parseInt("vv", radix);     // 1023
s = Integer.toString(i, radix);        // vv
```

## Perl

This can be done by using “hex” function to convert hex string into a number and “oct” function to convert octal or binary string into number

```perl 
my $no1 = hex(“0x64”);  #$no1 will be 100
my $no2 = oct(“144”);  #$no2 will be 100
my $no3 = oct(“0b1100100”); #$no3 will be 100
```

Formating a number to string in decimal, octal and hexadecimal format can be done using sprintf.

```perl
my $octString = sprintf("%#o", 12); # $octString is "014"
my $hexString = sprintf("%#x", 12); # $hexString is "0xc"
my $binString = sprintf("%#b", 12); # $binString is "0b1100" binary?
```

## C
The decimal can be formatted into hex, octal or binary string using sprintf

```c
char buffer [50];
sprintf (buffer, "%#x", 100);  //buffer is 0x64
sprintf (buffer, "%#0", 100); //buffer is 0144
```

## Bash
The decimal can be printed into hex, octal or binary using printf command as given below.

```bash
X=$( printf "%d" 64 )   #X = 100
X=$( printf "%x" 100 )   #X = 64
X=$printf "%o" 100 )   #X = 144
```

In bash variables are interpreted based on the leading character/digits. There are no types for the variables.

For example
X = 0144 is interpreted as octal value.
X = 0x64 is interpreted as hex value.
