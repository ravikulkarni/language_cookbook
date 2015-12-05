# Loops

## until..do / do..until

###Java
No ```until .. do``` or ```do..until``` loop in Java

### Perl
In Perl the do until  valuates the conditional expression and reiterates over the loop only when the expression returns false. Once the expression returns true, the loop ends.

An example is below
```perl
my $i=0;
do {
 # Do something with $i
 $i++;
} until $i >= 5;
```

### C

No ```until..do``` or ```do..until``` loop in C

### Bash

The until loop execute consequent-commands as long as test-commands has an exit status which is not zero. The return status is the exit status of the last command executed in consequent-commands, or zero if none was executed.

An example of this is

```bash
count=0
until [  $count -gt 5 ]; do
     # Do something with $count
      let count+=1
done
```

## while loop

### Java

The while loop in java evaluates the boolean expression and uses that to exit out of loop.
For example

```java
int count = 1;
while(count <5) {
	// Do something with count
	count ++;
}
```

### Perl

The while loop in Perl is also much like Java. An example is as below

```perl
my $count = 1;
while($count <5) {
	# Do something with count
	$count ++;
}
```

### C

A while loop in C is very much similar to Java,Perl. Example is below

```c
int count = 1;
while(count <5) {
	// Do something with count
	count ++;
}
```

### Bash
The while command executes consequent-commands as long as test-commands has an exit status of zero.
The return status is the exit status of the last command executed in consequent-commands, or zero if none was executed.
An example of this is

```bash
count=1
while [  $count -lt 5 ]; do
     # Do something with $count
      let count+=1
done
```

## do..while loop

### Java

The general syntax for this is where boolean expression is used to exit out of loop.

```java
do
{
  //Statements
}while(Boolean_expression);
```

An example is as below

```java
int i= 0;
do{
 //Do something with i;
 i++;
}while( i < 5 );
```

### Perl

In Perl the do while loop is similar to Java. Example is shown below

```perl
my $i = 0;
do {
 # Do something with $i
 $i++;
} while ($i <5);
```

### C

In C the do..while loop is similar to Java. An example is below

```c
int i= 0;
do{
 //Do something with i;
 i++;
}while( i < 5 );
```

### Bash
There is no ```do..while``` construct in Bash. Instead there is ```until``` loop


## for loop

### Java

The general syntax of for loop in java is

```java
for(initialization; Boolean_expression; update) {
  //Statements
}
```

An example of this is given below

```java
int i;
for (i=0; i<5;i++ ) {
	//Do something with i
}
```

There is another version of for loop whose general syntax is as below

```java
for(declaration : expression) {
  //Statements
}
```

This is usually used for array processing where the expression is array. An example of this is as follows

```java
int [] numbers = {1, 2, 3, 4, 5};
for(int x : numbers ){
   System.out.print( x );
    System.out.print(",");
}
```

### Perl

In Perl the general syntax of for loop is

```perl
for (EXPR; EXPR; EXPR) BLOCK
```

The EXPR in here are like Java/C. An example of this is as below

```perl
for (my $i=0;$i<5;$i++) {
# Do something with $i
}
```

You can place multiple variables into the expressions using the standard list operator (the comma):

There is also a foreach variant of for loop. Examples below show how to use them

```perl
my @intArray = (1,2,3,4,5);
foreach (@intArray) {
  #Do something with $_;
}
```

```perl
foreach my $index (@intArray) {
  #Do something with $index;
}
```

### C

The C has for loop is same as in Java. An example is shown below

```c
int i;
for (i = 0; i < 5; i++){
// Do something with i;
}
```

### Bash

The syntax of the for command is:
```bash
for name [ [in [words ...] ] ; ] do commands; done
```
Expand words, and execute commands once for each member in the resultant list, with name bound to the current member.
If ‘in words’ is not present, the for command executes the commands once for each positional parameter that is set, as if ‘in "$@"’ had been specified. The return status is the exit status of the last command that executes. If there are no items in the expansion of words, no commands are executed, and the return status is zero.

An alternate form of the for command is also supported:

```bash
for (( expr1 ; expr2 ; expr3 )) ; do commands ; done
```

First, the arithmetic expression expr1 is evaluated .
The arithmetic expression expr2 is then evaluated repeatedly until it evaluates to zero.
Each time expr2 evaluates to a non-zero value, commands are executed and the arithmetic expression expr3 is evaluated. If any expression is omitted, it behaves as if it evaluates to 1. The return value is the exit status of the last command in list that is executed, or false if any of the expressions is invalid.

```bash
for i in 1 2 3 4 5
do
  #Do something with $i
done
```
```bash
for i in {1..5}
do
  #Do something with $i
done
```

```bash
for i in {0..10..2}
 do
    #Do something with $i. Here the value starts from 0 to 10 with increments of 2
done
```

```bash
for (( i=1; i<=5; i++ ))
do
	#Do something with $i
done
```

## Loop Control


|   | exit out of loop | Next round of loop |
|---|------------------|--------------------|
| Java | break | continue |
| Perl | last | next |
| C | break | continue |
| Bash | break | continue | 


In addition to above Perl has redo keyword which re executes the loop without checking for the condition.


