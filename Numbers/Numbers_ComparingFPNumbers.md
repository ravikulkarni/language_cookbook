# Comparing numbers of floating type
This sections assumes that it is ok to round the floating point to certain precision before comparing them. If there are any floating point calculations, the results will have to be rounded to certain precision before comparing them to known value.

## Java

Using the method shown in the previous section the floating point number can be rounded to certain precision.

```java
DecimalFormat fmt =new DecimalFormat(“#.##”);
double d1 = 1.2300001;
double d2 = 1.2300002;
double v1 = Double.valueOf(fmt.format(d1));
double v2 = Double.valueOf(fmt.format(d2));
if(v1 == v2) {
	// Numbers are equal
} else {
	// Numbers are not equal
}
```

## Perl
Using the method in the previous section, the floating point can be rounded to certain precision before comparing. sprintf is a function to be used to do the rounding.

```perl
my $precision = 4;
my $num1 = 1.2345678;
my $num2 = 1.2345987;
if( sprintf(“%.${precision}g”, $num1) eq sprintf(“%.${precision}g”, $num2)) {
	#The numbers are equal.
}
```

## C

From the previous section the floating point number can be rounded to decided precision using sprintf and atof. Then it can be compared by the comparison operators.

```c
char buffer[256];
float v1 = 1.234767f;
float v2 = 1.234867f;
sprintf (buffer,"%.3f\n", v1);  // Precision set to 3 digits
float rV1 = atof(buffer);
sprintf (buffer,"%.3f\n", v2);  // Precision set to 3 digits
float rV2 = atof(buffer);
if(rV1 == rV2) {
	//Do something
}
```

## Bash
First round the floating point number to desired precision and then use comparison operator to compare them. An example is given below

```bash
X=$( printf "%0.2f\n" 3.1423456 )
Y=$( printf "%0.2f\n" 3.1475678 )
empty_string=""

if [ $X == $Y ]
then
echo "$X and $Y are equal"
else
echo "$X and $Y are not equal"
fi
```
