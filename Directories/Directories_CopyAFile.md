# Copying a file

## Java

Create an input and output stream and byte by byte copy everything to the destination file

```java
InputStream in = new FileInputStream(“InputFile.txt”);
OutputStream out = new FileOutputStream(“OutputFile.txt”);

 // Transfer bytes from in to out
byte[] buf = new byte[1024];
int len;
while ((len = in.read(buf)) > 0) {
    out.write(buf, 0, len);
}
in.close();
out.close();
```

## Perl

Use copy command from File::Copy module

```perl
use File::Copy;
$filetobecopied = "InputFile.txt";
$newfile = "OutputFile.txt";
copy($filetobecopied, $newfile) or die "File cannot be copied.";
```

## C

The file is copied by doing basic file operations - viz open a file to read and file to write, then read the bytes from the file to be read and write the bytes into file to be written to.
An example below shows how to do the file copy. Note that there is no error checking done here.

```c
	int fto, ffrom;
	char buf[4096];
	ssize_t nread;
	
                       //Initialize *from and *to to source and destination file respectively
	ffrom = open(from, O_RDONLY);
	fto = open(to, O_WRONLY | O_CREAT | O_EXCL, 0666);
	while (nread = read(ffrom, buf, sizeof buf), nread > 0) {
    	      char *optr = buf;
    	      ssize_t nbytes_written;

    	      do {
        	      	nbytes_written = write(fto, optr, nread);
        	      	 if (nbytes_written >= 0) {
            		         nread -= nbytes_written;
            		         optr += nbytes_written;
        		  } 
    	      } while (nread > 0);
	}

	if (nread == 0) {
		close(fto);
    		close(ffrom);
	}

```

## Bash

Use cp command

```bash
cp file1.txt file2.txt
```
