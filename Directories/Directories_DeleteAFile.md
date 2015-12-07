# Deleting a file

## Java
Use delete function on File object as given below

```java
boolean success = (new File("filename” )).delete();
if (!success) {
    // Deletion failed
}
```

## Perl
Use unlink function on the file as given below

```perl
$file = "newtext.txt";
unlink($file);
```

## C
Use unlink function to delete a file from a directory. 

```c
char nameBuff[32];
memset(nameBuff,0,sizeof(nameBuff));
strncpy(nameBuff,"/tmp/test.txt",14);
unlink(nameBuff);
```

## Bash
Use rm command

```bash
rm  filename.txt
```
