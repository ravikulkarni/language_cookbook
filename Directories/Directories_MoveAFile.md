# Moving a file

## Java
Use renameTo function on the file to be renamed/moved .

```java
// File (or directory) to be moved
File file = new File("filename.txt");

// Destination directory
File dir = new File("directoryname");

// Move file to new directory
boolean success = file.renameTo(new File(dir, file.getName()));
if (!success) {
    // File was not successfully moved
}
```

## Perl
Use ```rename``` call

```perl
$oldfile='/home/name1/old_file.txt';
$newfile='/home/name2/new_file.txt';
rename $oldfile, $newfile;
```

## C
The file moving can be done using rename function like below

```c
rename("/tmp/test.txt", "/tmp/test3.txt");
```

Alternatively, you can use copy the file and then deleting the file. The sources to do the both is given in the sections above.

## Bash
Use ```mv``` command

```bash
mv old_file.txt new_file.txt
```

