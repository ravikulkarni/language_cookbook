# Conditionals

## If then, if then else

### Java

In Java the syntax for if then else is
```java
if(conditional_expression){
 <statements>;
}
```

Or

```java
if(conditional_expression){
 <statements>;
} else if(conditional_expression) {

} else {

}
```

Examples below show how to use them

```java
int var = 10;

if (var == 10){
   // Do something when the var is 10
}
```

Or

```java
if (var == 10){
   // Do something when the var is 10
} else if(var == 9) {
   // Do something when the var is 9
} else {
   // Do something when the var is other than 9 and 10
}
```

### Perl

The Perl syntax for the if statement is as below.

```perl
if (CONDITION) {
	# Code block executed
	# if condition is true.
} else {
	# Code block executed
	# if condition is false.
}

if (CONDITION_ONE) {
	# Code block executed
	# if condition one is true.
} elsif (CONDITION_TWO) {
	# Code block executed
	# if condition two is true.
} else {
	# Code block executed
	# if all other conditions are false.
}
```

Example is below

```perl
my $var = 10; // set
if($var == 10) {
	#Do something when the var is 10
} elsif ($var ==9) {
	#Do something when the var is 9
} else {
# Do something when the var is other than 9 and10
}
```

### C
The syntax of if then else statements in C is as below

```c
if (expression)
 statement;
```

OR

```c
if (expression) {
	Block of statements;
}
```

OR

```c
if (expression){
	Block of statements;
} else {
	Block of statements;
}
```

OR

```c
if (expression) {
	Block of statements;
} else if(expression) {
	Block of statements;
} else {
	Block of statements;
}
```

An example of this is as below similar to what it is in Java

```c
int var=10;
if (var == 10){
   // Do something when the var is 10
} else if(var == 9) {
   // Do something when the var is 9
} else {
   // Do something when the var is other than 9 and 10
}
```

### Bash

The bash syntax for if then else statement is as below

```bash
if test-commands; then
	consequent-commands;
[elif more-test-commands; then
	more-consequents;]
[else alternate-consequents;]
fi
```

Example is given below

```bash
var=10
if [ $var == 10]; then
	#Do something when $var is 10
fi
```

OR

```bash
if [ $var == 10]; then
	#Do something when $var is 10
else
#Do something when $var is not 10
fi
```

OR

```bash
if [ $var == 10]; then
	#Do something when $var is 10
elif [$var == 9]; then
	#Do something when $var is 9
else
	#Do something when $var is not 9 or 10
fi
```

## switch/case

### Java

The Java syntax for the switch statement is as below

```java
switch(control_expression){
 case expression 1:
 <statement>;
 case expression 2:
 <statement>;
  ...
  ...
 case expression n:
 <statement>;
 default:
 <statement>;
}//end switch
```

An example is shown

```java
int var = 10;

switch (var) {
  case 10:
   //Do something when the value of var is 10      
   break;
  case 9:
   //Do something when the value of var is 10      
   break;
  default:
  //Do something when the value of var is not 9 or 10      
  break;
}
```

To have statements in switch fall through, do not use break statements

### Perl

In Perl the switch statement needs using Switch module.
The general syntax would be as below

```perl
switch (control_expression) {
	case 1 { #block of code  }
	case 2  { #block of code }
	else { #default block of code}
}
```

An example below shows how to use the switch

```perl
use Switch;
my $var = 10;
switch ($var) {
	case 10 { #Do something when the $var is 10  }
	case 9  { #Do something when the $var is 9 }
	else { #Do something when the $var is not 10 or 9}
}
```

To have fall through added use the "next" statement as given below

```perl
use Switch;
my $var = 10;
switch ($var) {
	case 10 { #Do something when the $var is 10; next  }
	case 9  { #Do something when the $var is 9 }
	else { #Do something when the $var is not 10 or 9}
}
```

To enable fall through of the statements by default, use Switch module with fall through as below
```perl
use Switch 'fallthrough';
```

### C

The general syntax is

```c
switch( expression ){
 case constant-expression1:    statements1;
 [case constant-expression2:    statements2;]    
 [case constant-expression3:    statements3;]
 [default : statements4;]
}
```

An example of this is

```c
int var = 10;
switch( var ){
  case 10 :
 	//Do something when the var is 10
 	break;
  case 9 :
 	//Do something when the var is 9
 	break;
  default  :
 	//Do something when the var is not 9 or 10
 	break;
}
```

The statements fall through if the break statement is not used.

### Bash

The syntax of the case command is:

```bash
case word in [ [( pattern [| pattern]...) command-list ;;]... esac
```

An example below shows its use

```bash
var=10
case $var in
  10) echo "ten";;
  9)  echo "nine";;
  *) echo "Not 9 or 10";;
esac
```

Using ```;&``` in place of ```;;``` causes execution to continue with the command-list associated with the next clause, if any. Using ‘;;&’ in place of ‘;;’ causes the shell to test the patterns in the next clause, if any, and execute any associated command-list on a successful match.
	
