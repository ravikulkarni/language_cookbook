# Listing hidden files in directory.

## Java
For hidden files, there is no difference in the program.

## Perl

Use ‘.*‘ for the file name selection

```perl
my @hidden = glob( '.*' );
```

## C
Use the program to process files in the directory from the previous sections. As a part of processing the file, print  if the file is hidden with the code given below

```c
void print _if_hidden(const char *name) {
  if(name[0] == '.' && strcmp(name, ".") != 0 && strcmp(name, "..") != 0) {
  	printf(“%s”, name);
   }
}
```

## Bash

Passing -a as an argument lists all files including hidden files.

```bash
ls -a
```
