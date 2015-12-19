# Using random access IO

## Java
This functionality is possible with the channel interface. This interface supports notion of a current position.  Methods enable you to set/query the position, read /write the data to that position.

An example is given below write a string at the beginning and end of file. This can be changed to write to any position in the file.

```java
  String s = "Test Sentence 1\n";
   byte data[] = s.getBytes();
   ByteBuffer out = ByteBuffer.wrap(data);
   try {
   	FileChannel fc = new RandomAccessFile("d.sh","rw").getChannel();
   
	// Write "Test Sentence 1" at the beginning of the file.
   	fc.position(0);
   	while (out.hasRemaining()) {
  	 fc.write(out);
   	}
   	out.rewind();
  	
   	// Move to the end of the file.  Then write "Test Sentence 1" again.
   	long length = fc.size();
   	fc.position(length-1);
   	while (out.hasRemaining())
  	 fc.write(out);
   } catch (IOException x) {
   	System.out.println("I/O Exception: " + x);
   }    
```

## Perl
Perl provides a seek function for moving to certain position and read certain chunk of data.
Using a combination of seek and read call, random access to file can be achieved.

```
seek FILEHANDLE, POSITION, WHENCE sets the filehandle position within the file in bytes where WHENCE can be set to SEEK_SET for start of file, SEEK_CUR for the current position and SEEK_END for the end of file.
read FILEHANDLE, SCALAR, LENGTH reads LENGTH characters from FILEHANDLE into the SCALAR variable.
```

```perl
use Fcntl;
my $filename = shift;

open FH, "+<somefile.txt" or die "Could not open file";

# Read bytes 64-127 into $text
seek(FH, 64, SEEK_SET);

my $text, $newtext
#set $newtext to something;
read(FH,$text,64);
seek(FH, 64, SEEK_SET);
print FH $newtext
close(FH);
```

In the above example, if the $newText is better than $text are different length then some text will get overwritten.

## C
C provides a seek function for moving to certain position and read certain chunk of data.
Using a combination of fseek and fread call, random access to file can be achieved.

```c
 FILE* fd = NULL;
 char buff[100];
 memset(buff,0,sizeof(buff));
 fd = fopen("test.txt","rw+");
 //No error checking done
 int bytesRead= fread(buff,1,100,fd);
 //No error checking done  
 //Seek to position 15
 fseek(fd,15,SEEK_CUR));
 //No error checking done. Write to that location
 int bytesWritten= fwrite(buff,SIZE,strlen(buff),fd);
 //No error checking done.
 fclose(fd);
```

## Bash

Bash does not support random IO.
