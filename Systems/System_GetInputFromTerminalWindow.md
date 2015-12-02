# Reading input from terminal window

## Java
The System class in java has an inputstream that is to be used to read input from terminal window.  Example of that is given below

```java
InputStreamReader isr = new InputStreamReader( System.in );
BufferedReader br = new BufferedReader( isr );
String input = b_reader.readLine();
```

## Perl

The STDIN input handle is to be used to get input from user. Remember to chomp the data received from the handle so that it does not contain the carriage return character.
The handles is written as <STDIN> or also abbreivated as <>
Example below shows how to use it.

```perl
print "Enter some string";
chomp ($str = <>);
```

## C

In C the user input can be read by using either “scanf”, “gets” calls. But a better option is to use “fgets” call. The string returned by this call may or may not have new line character depending on the size of buffer. So it needs to be checked and replaced with null terminator.  Example below shows how to do that.

```c
char text[256];
fputs("Enter something: ", stdout);
fflush(stdout);
if ( fgets(text, sizeof text, stdin) != NULL ) {
  char *newline = strchr(text, '\n'); /* search for newline character */
  if ( newline != NULL ) {
        *newline = '\0'; /* overwrite trailing newline */
  }
     printf("text = \"%s\"\n", text);
}
```

## Bash
The user input is read into the program using “read” call. The call accepts different options regarding how to interpret the data into variable.
Below are the 2 examples.

```bash
echo "Enter name"
read name
#Do something with $name

echo -n "Enter Yes or No"
read -n 1 ans # Reads the first character.
#Do something with $ans
```

