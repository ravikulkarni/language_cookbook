# Finding number of unread bytes.

## Java
In java the bytes unread from the byte stream is calculated from the read call of an input stream. An example is given below. In this example, the read call returns the bytes read which are then added to offset to continues the reading of bytes.

```java
InputStream is = new FileInputStream(file);

long length = file.length();
//Assuming that the file size is less than Integer.MAX
byte[] bytes = new byte[(int)length];

int offset = 0;
int numRead = 0;
while (offset < bytes.length
      && (numRead=is.read(bytes, offset, bytes.length-offset)) >= 0) {
   offset += numRead;
}

if (offset < bytes.length) {
   throw new IOException("Could not completely read file "+file.getName());
}

is.close();
```

## Perl

Use the FIONREAD ioctl call:

```perl
$size = pack("L", 0);
ioctl(FH, $FIONREAD, $size)     or die "Couldn't call ioctl: $!\n";
$size = unpack("L", $size);
# $size bytes can be read
```
Make sure the input filehandle is unbuffered (because you've used an I/O layer like :unix on it), or use only sysread. Also this depends on the system having FIONREAD request or ioctl call.

## C

In C the unread bytes can be calculated based on the number of bytes read. The fread call returns the bytes read in that call. An example is given below

```c
FILE* fp = NULL;
char buff[10000];
memset(buff,0,sizeof(buff));
 
fp = fopen("file_to_be_read.txt","r");
 
printf("\n File read %d \n",fread(buff,1,10000,fp));
 
if(fp!=NULL) fclose(fp);  
```

The actual bytes read may be different than what was requested to be read.

## Bash

Bash has no calls for this.
