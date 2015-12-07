# Finding files

## Java

The files in the directory can be found by using FileFilter class as shown below

```java
// The list of files can also be retrieved as File objects
File dir = new File(“dirName”);
File[] files = dir.listFiles();

// This filter only returns directories
FileFilter fileFilter = new FileFilter() {
    public boolean accept(File file) {
        return file.isDirectory();
    }
};
files = dir.listFiles(fileFilter);
```

## Perl
Use File:Find module and pass handler subroutune where the file is processed.

```perl
use File::Find;

sub d {
my $file = $File::Find::name;
print "$file\n";
return unless -f $file;
#Do something with file
print "$file\n";
}
my @dirList;
push @dirList, ".";
find(\&d, @dirList);
```

## C
This is going to use the same code as for processing files and deleting directory. The processing file example in section above gives a place where the file is identified. The code for deleting a directory show how to build complete path for that file. Please refer to the code for deleting directory. Remove the ```unlink``` and ```rmdir``` calls in that code.

## Bash

Use find command as given below.

```bash
find dirName -type f
```
