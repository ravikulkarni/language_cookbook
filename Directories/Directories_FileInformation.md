# Getting information about files.

## Java
Use lastModified function call on File object to get the last modified time

```java
File file = new File("filename");

// Get the last modified time
long modifiedTime = file.lastModified();
// 0L is returned if the file does not exist
```

Use the length function call on File object to get the size of the file

```java
File file = new File("infilename");

// Get the number of bytes in the file
long length = file.length();
```

## Perl
Use stat function call and capture the returned array into variables . Please refer to sample below that gives what is returned by stat call.

```perl
($dev,$ino,$mode,$nlink,$uid,$gid,$rdev,$size, $atime,$mtime,$ctime,$blksize,$blocks)            = stat($filename);
```

Not all fields are supported on all filesystem types. Here are the meanings of the fields:
```
 0 dev      device number of filesystem
 1 ino      inode number
 2 mode     file mode  (type and permissions)
 3 nlink    number of (hard) links to the file
 4 uid      numeric user ID of file's owner
 5 gid      numeric group ID of file's owner
 6 rdev     the device identifier (special files only)
 7 size     total size of file, in bytes
 8 atime    last access time in seconds since the epoch
 9 mtime    last modify time in seconds since the epoch
10 ctime    inode change time in seconds since the epoch (*)
11 blksize  preferred block size for file system I/O
12 blocks   actual number of blocks allocated
```

## C
Use stat function to get the information on a file. The stat structure has lot of information that it captures. Please refer to stat structure for all the information that can be made available for a file

The call needs a pointer to stat structure in which it populates the data

```c
 struct stat fileStat;
 stat("/home/ravisarika/book/sample_code/book/directories/dir.c",&fileStat);
```

## Bash
Use ```stat``` function

```bash
stat [OPTION] file
```

Display file or file system status.
```
      -L, --dereference
             follow links
      -f, --file-system
             display file system status instead of file status
      -c  --format=FORMAT
             use  the  specified FORMAT instead of the default; output a new-
             line after each use of FORMAT
      --printf=FORMAT
             like --format, but interpret backslash escapes, and do not  out-
             put  a  mandatory  trailing  newline.   If  you  want a newline,
             include \n in FORMAT.
      -t, --terse
             print the information in terse form
      --help display this help and exit
      --version
             output version information and exit
      The valid format sequences for files (without --file-system):
      %a     Access rights in octal
      %A     Access rights in human readable form
      %b     Number of blocks allocated (see %B)
      %B     The size in bytes of each block reported by %b
      %C     SELinux security context string
      %d     Device number in decimal
      %D     Device number in hex
      %f     Raw mode in hex
      %F     File type
      %g     Group ID of owner
      %G     Group name of owner
      %h     Number of hard links
      %i     Inode number
      %n     File name
      %N     Quoted file name with dereference if symbolic link
      %o     I/O block size
      %s     Total size, in bytes
      %t     Major device type in hex
      %T     Minor device type in hex
      %u     User ID of owner
      %U     User name of owner
      %x     Time of last access
      %X     Time of last access as seconds since Epoch
      %y     Time of last modification
      %Y     Time of last modification as seconds since Epoch
      %z     Time of last change
      %Z     Time of last change as seconds since Epoch
      Valid format sequences for file systems:
      %a     Free blocks available to non-superuser
      %b     Total data blocks in file system
      %c     Total file nodes in file system
      %d     Free file nodes in file system
      %f     Free blocks in file system
      %C     SELinux security context string
      %i     File System ID in hex
      %l     Maximum length of filenames
      %n     File name
      %s     Block size (for faster transfers)
      %S     Fundamental block size (for block counts)
      %t     Type in hex
      %T     Type in human readable form
```

