# Locking a file

## Java

This can be done using class java.nio.channels.FileLock. This class maps to the native operating system. The lock has to be created on channel for file which is in write mode. Using RandomAccessFile to open a file in read write mode is one way to open the channel for locking.
Example is given below

```java
try {
  RandomAccessFile raf = new RandomAccessFile("d.sh","rw");
  java.nio.channels.FileLock lock = raf.getChannel().lock();
  //Do something with raf.
   lock.release();
} catch (IOException e){
	//Do something with the exception
}
```

## Perl
In Perl the file can be locked using flock. The flock takes file handle and the locking operation.
```perl
flock FILEHANDLE OPERATION
```
The OPERATION value can be
* 1 Shared Lock
* 2 Exclusive lock
* 4 non blocking lock
* 8 unlock

If the file is closed, it is automatically unlocked.

Below is an example of how to use it

```perl
$file = "file_to_be_locked.txt";
open(FH, ">$myfile") || die;
flock(FH, 2);
# Write something with the (FILEHANDLE,
flock(, 8);
close(FH);
```

## C

Just like in Perl there is a method call flock that is used to lock the file. An example is given below

```c
FILE *fp=fopen(file.txt,"r+");
flock(fileno(fp),LOCK_EX);
/*do necessary stuff here*/
flock(fileno(fp),LOCK_UN);
fclose(fp);
```

## Bash
A simple way to get that is to create a lock directory - the mkdir command. It will
create a given directory only if it did not exist before, and set a successful exit code
it will set an unsuccesful exit code if an error occours - for example if the given directory already existed
With mkdir it seems, we have our two steps in one simple operation. A (very!) simple locking code might look like this now:

```bash
if mkdir /var/lock/mylock; then
 echo "Locking succeeded" >&2
else
 echo "Lock failed - exit" >&2
 exit 1
fi
```
