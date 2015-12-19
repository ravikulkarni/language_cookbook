# File Reading

## Java
In java file can be read in byte array or as text file. Below is an example of how file is read using bytes.

```java
try{
   File file = new File(“picture.jpg”);
   InputStream is = new FileInputStream(file);

    // Get the size of the file
    long length = file.length();
   
    if (length > Integer.MAX_VALUE) {
        // File is too large
    }

    // Create the byte array to hold the data
    byte[] bytes = new byte[(int)length];

    // Read in the bytes
    int offset = 0;
    int numRead = 0;
    while (offset < bytes.length
           && (numRead=is.read(bytes, offset, bytes.length-offset)) >= 0) {
        offset += numRead;
    }

    // Ensure all the bytes have been read in
    if (offset < bytes.length) {
        throw new IOException("Could not completely read file "+file.getName());
    }

    // Close the input stream and return bytes
    is.close();
} catch(IOException) {
	//Do something with IOException
}
```

Alternatively, text can be read from a file as below

```java
try {
    BufferedReader in = new BufferedReader(new FileReader("infilename"));
    String str;
    while ((str = in.readLine()) != null) {
        //process str ;
    }
    in.close();
} catch (IOException e) {
}
```

## Perl

If you want to read all the lines into an array and then process line by line, below is a method to do that.

```perl
open FILE, "<", "filename.txt" or die $!;
my @lines = <FILE>;
#Do something with the @lines
close(FILE);
```

Or

if you want to process line after reading it, then below is a way to do that.

```perl
open FILE, "<", "filename.txt" or die $!;
while (<FILE>) {
 print $_;
}
close(FILE);
```

For reading only a few characters at a time, below is an example. Here read call reads only 4 characters at a time.

```perl
open FILE,"<", "picture.jpg" or die $!;
binmode FILE;
my ($buf, $data, $n, $offset);
while (($n = read FILE, $data, 4) != 0) {
 #print "$n bytes read\n";
 $buf .= $data;
}
#Do something with $buf
close(FILE);
```

## C

In C the file can be opened using command open. The modes for opening the file are as below
* "r" - read the file
* "w" - write the file
* "a" - append to the file
* "r+" - read and write to the file
* "w+" - read and write, overwrite the file
* "a+" - read and write, append

To read the file one character at a time, use

```c
FILE *filepointer;
int character;
filepointer=fopen("file.txt", "r");
if (filepointer==NULL) { /* error opening file returns NULL */
         /*Show some error message*/
}
while ((character=fgetc(filepointer)) != EOF) {
        /* Do something with the character */
}
fclose(filepointer); /* close the file */
```

If more than one characters are to be read then use fgets instead of fgetc

Code below should shows the use of fgets

```c
char input[80];
fgets(input, sizeof(input), filepointer);
```

## Bash
The bash code to read the file line by line is shown below.

```bash
while read line         
do         
   echo-e "$ line \ n"         
done <file.txt         
```
