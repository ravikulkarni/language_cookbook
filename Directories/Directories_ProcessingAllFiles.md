# Processing all files in a directory

## Java

The functions used here are isDirectory which checks if the directory/file object is a directory or a file. If it is a directory the function is called recursively.

```java
public static void visitAllFiles(File dir) {
    if (dir.isDirectory()) {
        String[] children = dir.list();
        for (int i=0; i<children.length; i++) {
            visitAllFiles(new File(dir, children[i]));
        }
    } else {
        process(dir);
    }
}
```

## Perl

Use opendir to open the directory and then readdir to retrieve every filename. Note that the filenames returned by readdir do not include the directory name.

```perl
opendir(DIR, $dirname) or die "can't opendir $dirname: $!";
while (defined($file = readdir(DIR))) {
   # do something with "$dirname/$file"
}
closedir(DIR);
```

## C
This is acheived by opening a directory and reading all the entries. If the entry is a directory call the function recursively on that directory. Sample code is given below (without error checking)

```c
void processFiles(const char *dirname) {
	DIR *directory;
	struct dirent *dir_entry;
	directory = opendir(dirname);
	dir_entry = readdir(directory);

	do {
    		if (dir_entry->d_type == DT_DIR) {
        			char path[1024];
        			int len = snprintf(path, sizeof(path)-1, "%s/%s", name, dir_entry->d_name);
        			path[len] = 0;
        			if (strcmp(dir_entry->d_name, ".") == 0 || strcmp(dir_entry->d_name, "..") == 0)
            				continue;
        			processFiles(path);
    		}  else  {
        			// Process the file dir_entry->d_name;
		}
	} while (dir_entry = readdir(directory));
	closedir(directory);
}
```

## Bash

The files can be found using find command. An example is given below

```bash
find parentDirectory -type f
```

The parentDirectory is the directory under which all the files are to be processed. The command returns the file names and can be used to process one by one.

