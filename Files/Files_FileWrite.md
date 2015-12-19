# File Writing

## Java
In Java characters can be written into a file using FileWriter and BufferedWriter class. Example is given below.

```java
try{
 // Create file
 FileWriter fstream = new FileWriter("out.txt");
 BufferedWriter out = new BufferedWriter(fstream);
 out.write("Some text");
 //Close the output stream
 out.close();
}catch (Exception e){//Catch exception if any
 System.err.println("Error: " + e.getMessage());
}
```

## Perl
Below is an example of writing  the file. The $string is the data to be written into the file. Please remember to close the file after writing done.

```perl
my $str = “Some text”;
open FILE, ">filetobewritten.txt" or die $!;
print FILE $str;
close FILE;
```

## C

In C use fputc to write a character to the file. Or use fprintf/fputs to write a string to the file.
Example use of the calls is below

```c
fputc(character, filepointer);
fprintf(filepointer, "Write something!\n");
fputs("Write something!\n", filepointer);
```

Where the filepointer is created as below

```c
FILE *filepointer;
filepointer=fopen("file.txt", "a");
```

## Bash

In bash text can be written into a file by simply redirecting it using “>>” or  “>”.  “>” will create or overwrite a file where as “>>” will append the file

```bash
echo “Text to be written into a file” >> file.txt
```
