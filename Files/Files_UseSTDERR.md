# Using Standard error handle

## Java
In Java the System class has the standard error stream

This can be accessed by
```java
System.err
```
Example is

```java
System.err.println(“This is a test error string”);
```

## Perl
In perl the standard output handle is ```STDERR```

Example

```perl
print STDERR ‘This has to be printed out on stdout’;
```

## C
In the C programming language the standard error streams is attached to the existing Unix file descriptors 2 . In a POSIX environment the <unistd.h> definitions STDERR_FILENO should be used instead rather than magic numbers. File pointers stderr are also provided.

## Bash

1 represents stdout handle.
All the command output for echo is sent to stdout by default. If there is need to redirect stderr to stdout then it is done as given below

```bash
echo "test" 2>&1
```
