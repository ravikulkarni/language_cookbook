# Variables

## Getting environment variables

### Java
There is a method in System class called getEnv that returns all the environment in form of Map object. The object can be iterated over to get the key and values

Example of that is below. The environment variable that is read is PATH.

```java
Map<String, String> env = System.getenv();
String pathValue = env.get(“PATH”);
```

### Perl
In Perl the environment variables are stored in special hash named %ENV. To access particular environment variable, use that environment variable as key of that hash. Following can be used as an example to get the PATH variable.

```perl
$userName =  $ENV{'PATH'};
```

### C

There is a function named getenv declared in stdlib.h that can be used to get the environment variables
```c
char * pPath = getenv ("PATH");
```

### Bash

Getting the environment variable for bash is probably the easiest

Just use the variable like below
```bash
echo $PATH
```

## Setting environment variables

### Java
In Java when the VM starts it makes a copy of the environment variable. There is no function to write the environment variable in the same process as the VM

### Perl
In perl for the current running process the environment variable can be set just by simply manipulating %ENV hash. In example below, the environment variable PATH is updated to a new value.

```perl
$ENV{‘PATH’} = “new Path”;
```

### C
In C this can be done using putenv method as shown below. The environment PATH is modified in the example below.

```c
putenv("PATH=C:\");
```

### Bash

In Bash, this is also one of the easy to do. Just set the environment variable as shown below.

```bash
PATH = “C:\”
```
## Looping over arguments passed to a script

### Java
In Java the arguments are passed as an array. To loop over arguments is looping over the array.

Below is the signature of the main method in Java. The main method takes a string array as an argument. This array keeps the arguments passed to the java  program when it is executed.
```java
public static void main(String args[]) {
    for(int i=0;i<args.length;i++) {
        //args[i] is the argument
    }
}
```

### Perl
In perl the array which stores the argument is @ARGV. Looping through that array will give each argument.
```perl
foreach (@ARGV) {
       print "$_\n";
}
```

### C
In c the main method can have one of the two types of signature - one which does not take arguments and another on where the arguments to that method are argc and argv.
The method signatures looks something like this.
```c
void main() and
void main(int argc , char** argv)
```
With C the arguments are stored in array pointed by argv. Example is shown below. Here argv is pointer to two dimensional array.

```c
int count;
for( count = 0; count < argc; count++ )
   printf( "  argv[%d]   %s\n", count, argv[count] );
}
```

### Bash

As with the other languages compared in this book, the arguments are stored in array $@. Below is a way to access them

```bash
for argument in "$@"
do
   echo "$argument"
done
```
Here its necessary to use “$@” instead of $@ so that the parameters with spacing can also be processed.


## Counting total arguments

### Java
In Java the arguments are passed to the main procedure in form of array. The length of that array is the total number of arguments passed.

```java
public static void main (String args[]).
```

In this case the number of arguments are given by ``` args.length ```

### Perl

Perl command line arguments stored in the special array called ```@ARGV```.
Use ```scalar(@ARGV)``` to get total number of passed argument to a perl script.

### C

In C of the 2 signatures of main method, the number of arguments is passed as one of the parameters in the signature of main method which takes argument.

```c
int main ( int argc, char **argv )
```

The argc here is the argument count.This includes the executable name that is called at the location 0 of the argv array.

### Bash

In Bash the arguments count is found out by $#.

For example
```bash
#myscript arg1 arg2
The $# will be 2 in this case.
```

