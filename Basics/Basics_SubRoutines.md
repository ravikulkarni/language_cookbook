# Subroutines/Functions

## Method/function/subroutine declaration

### Java
Method declarations have six components, in order:

	* Modifiers—such as public, private, protected.
	* The return type—the data type of the value returned by the method, or void if the method does not return a value.
	* The method name—the rules for field names apply to method names as well, but the convention is a little different.
	* The parameter list in parenthesis—a comma-delimited list of input parameters, preceded by their data types, enclosed by parentheses, (). If there are no parameters, you must use empty parentheses.
	* An exception if the method throws any..
	* The method body, enclosed between braces—the method's code, including the declaration of local variables, goes here.

An example shown below can be helpful in understanding

```java
public int method1(int argument1) {
	int i = 0;
//Method body here.
	return i; //(or any int return value)
}
```

```java
public int[] method1(int argument1, int[] arr) throws IOException {
	int a[] = new int[5];
	//Method body here.
	return a; //(or any int array)
}
```

These functions are called by their names and appropriate arguments are passed to it. For example, the methods above will be called as

```java
int arg1 = 0;
int argArr [] = new int[10];
//Initialize  arg1 and argArr
int retVal[] = method1(arg1, argArr);
```

### Perl

A commonly used method of defining methods is in the format below
```perl
sub NAME BLOCK
```

For example of one with no prototype

```perl
sub method1 {
	//Take arguments
}
```

A function with prototype example is

```perl
sub pi ()           { 3.14159 }
sub test (\@)     called as test @some_array
```
The function is called as below

```perl
method1();
pi();
```

### C
The C function is definition is
In C the functions are declared in form

```c
returnType functionName (list of arguments with their types);
```

An example is

```c
int method1 (int argument1)
```

The function definition adds block to the definition.
```c
int method1 (int argument1) {
   return some_int;
}
```
Adding the function to the header file creates an interface for using the function in the library.

The function is called as below
```c
int a = method1(10);
```

### Bash

The general syntax of bash function is

```bash
function function_name {
  command...
}
```

OR

```bash
function_name () {
  command...
}
```

Example of this is

```bash
function method1 {
	#This method multiplies
	number1=$1
 	number2=$2
 	echo $[number1*number2]
}
```

Call this function as below

```bash
result = $(method1 2 3)
```

## Accessing subroutine arguments

### Java
In Java, the method signature has arguments defined and can be used with their variable names

For example

```java
public int multiply(int number1, int number2){
	// argument1 and argument2 are arguments that can be used with their names.
	return number1 * number2;
}
```

### Perl

In Perl there are 3 ways to access arguments

One way is to get the arguments as ```$_[0]```, ```$_[1]``` and so forth.
Second way is to get the arguments using shift command which pops element one by one from array.
Third way is to assign the values of ```@_``` to a list of variables

Lets say for example there is a function to multiply 2 numbers and is called as follows
```perl
multiply(2,3)
```
Here is how the functions would take the argument

```perl
sub multiply {
  my $number1 = $_[0];
  my $number2 = $_[1];
  return $number1 * $number2;
}

sub multiply {
  my $number1 = shift;
  my $number2 = shift;
  return $number1 * $number2;
}

sub multiply {
  my ($number1, $number2) = @_;
  return $number1 * $number2;
}
```

The function is called as below
```perl
multiply(2,3)
```

### C
In C, the method signature has arguments defined and can be used with their variable names

For example

int multiply(int number1, int number2){
	// argument1 and argument2 are arguments that can be used with their names.
	return number1 * number2;
}

### Bash

In Bash the argument are accessed by ```$1```, ```$2``` and so on.
```$0``` being the name of the script

For example

```bash
function multiply {
       number1 = $1
      number2 = $2
      echo  number1*number2
}
```

## Making variables private in a function

### Java,C
For Java and C the variables declared in the function block have local scope. There is no special keyword for making the variables local

### Bash, Perl
A variable is made local by using "local" keyword. A variable declared as local is one that is visible only within the block of code in which it appears. It has local scope. In a function, a local variable has meaning only within that function block.


## Return information to caller.
The table shows the how to return values to the caller of the function

### Java
Use ```return``` statement

### Perl
Use ```return``` statement or the value of last statement executed is returned.

### C
Use ```return``` statement

### Bash
Use ```echo``` statement to send result to output and then capture it from calling code.

## Error handling.

### Java

The error handling in java is via exceptions. There are 2 types of exceptions viz checked exceptions (Exception and its subclasses) and unchecked exceptions (RuntimeException, Error, and their subclasses)
The checked exceptions have to be caught by exception handler. The exception is thrown back to caller until the exception is handled by try catch block. If the exception is not caught then it exits the program or thread in which it is thrown but not caught. The checked exception thrown in a method but not caught has to be declared by throws clause.
For example

```java
public int method1() throws CustomException {
	//Throws CustomException on some error condition.
//There is no try catch block to handle the Custom Exception
}
```

OR

```java
public int method1() {
	try {
		//Throws CustomException on some error condition.
} catch (CustomException e){
	//Do something else when the CustomException is thrown.
}
}
```

In above example, there could be any checked exception in place of CustomException. CustomException is just used as an example

### Perl

There are multiple ways to catch errors. What method to use is based on the situation

#### If, unless

Using if, unless can be used to decide if the expression results in passing condition or not. For example, if or unless block can be used to see if the function returned failure (0) or success (1).

```perl
if(chdir('/tmp')){
   //Do something here after changing directory.
}
unless(chdir('/tmp')) {
   //Do something when the directory is not changed.
}
```

The error is kept in variable ```$!```.

#### Warn Function

The warn function just prints message to STDERR

```perl
chdir('/tmp') or warn "Can't change directory";
```

When called from the module, it prints the module name and line number.

#### Die Function

The die function prints message to STDERR and then exits (i.e terminates the execution of the script).

```perl
chdir('/tmp') or die "Can't change directory";
```

#### Carp Module

This module

In Perl program this module is called by adding following line in the perl file.

```perl
use Carp;
```

The Carp modules provides following 4 functions that return information about the calling script without actually exiting the script and printing the script name.

```perl
carp function
carp "Error in some module";
```

The carp function prints the message in addition to the module and the line nuber where this carp function was called.

#### cluck Function

```perl
cluck "Error in some module";
```

The cluck function prints
- the message
- the module and the line nuber where this cluck function was called.
- a stack trace of all the modules that led to the function being called, including information on the original script.

#### croak Function

The croak function prints the message, reports the caller one level up and then exits the script.

#### confess Function

The confess function prints
- the message
- the module and the line nuber where this cluck function was called.
- a stack trace all the way up to the origination script.
- exits the script

### C

C does not provide direct support for error/exception handling. The program is supposed to test return values from functions and act accordingly. In a worst case scenario where there is an unavoidable error and no way to recover from it, the program should log the error and "gracefully" terminate the program.

There is an external variable called "errno", accessible by the programs after including <errno.h> - that file comes from the definition of the possible errors that can occur in some Operating Systems when programs ask for resources. Such variable indexes error descriptions accessible by the function 'strerror( errno )'.

#### Signals

In some cases, the environment may respond to a programming error in C by raising a signal. Signals are events raised by the host environment or operating system to indicate that a specific error or critical event has occurred

To handle signals, a program needs to use the signal.h header file. A signal handler will need to be defined, and the signal() function is then called to allow the given signal to be handled. These signal handlers should ensure that resources are properly cleaned up before the program terminates.

#### setjmp

The setjmp function can be used to emulate the exception handling feature. The first call to setjmp provides a reference point to returning to a given function, and is valid as long as the function containing setjmp() doesn't return or exit. A call to longjmp causes the execution to return to the point of the associated setjmp call.


### Bash

The errors returned by commands in BASH shell scripts with can be caught with "$?". If a program gives anything but a zero return code, there has been an error of some type. The value of "$?" can be checked for 0 to determine if there are any errors

```bash
if [ $? != 0 ]; then
{
   # Do something when there is error.
} fi
```

#### trap

The trap command allows execution of commands when a signal is received by your script. It works like this:

```bash
trap arg signals
```

"signals" is a list of signals to intercept and "arg" is a commands to execute when one of the signals is received.

Example below shows how some commands can be used executed when any of the OS signals are received.

```bash
trap "cd /tmp/;echo 'error'> error_log; exit" SIGHUP SIGINT SIGTERM
```

Note that the SIGKILL or signal 9 cannot be trapped.

Instead of writing all the commands to execute on getting a signal, the trap command can have a function name mentioned

Example is below

```bash
function cleanUp {
   # Perform cleanup
   exit
}

trap cleanUp SIGHUP SIGINT SIGTERM
```

