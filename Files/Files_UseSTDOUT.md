# Using Standard output handle

## Java
In Java the System class has the standard output stream

This can be accessed by
```java
System.out
```

Example is

```java
System.out.println(“This is a test string”);
```

## Perl

In perl the standard output handle is ```STDOUT```

Example

```perl
print STDOUT ‘This has to be printed out on stdout’;
```

## C

In the C programming language the standard output is attached to the existing Unix file descriptors 1. In a POSIX environment the <unistd.h> definitions STDOUT_FILENO should be used instead rather than magic numbers. File pointers stdout is also provided.

## Bash
1 represents stdout handle.
All the command output for echo is sent to stdout by default. If there is need to redirect stderr to stdout then it is done as given below

```bash
echo "test" 2>&1
```
