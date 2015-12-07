# Renaming a file

## Java

Just like moving a file, use function renameTo on File object created.

```java
// File (or directory) with old name
File file = new File("oldname");

// File (or directory) with new name
File file2 = new File("newname");

// Rename file (or directory)
boolean success = file.renameTo(file2);
if (!success) {
    // File was not successfully renamed
}
```

## Perl
Use rename call passing the old file name and new file name as argument.

```perl
rename old_file_name.txt , new_file_name.txt
```

## C
This is using the same rename call as for moving a file.

## Bash
Use ```mv``` command passing old file name and new file name as an argument.

```bash
mv old_file_name.txt , new_file_name.txt
```
