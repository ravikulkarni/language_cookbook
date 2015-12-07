# Removing a directory and its contents

## Java

Removing the directory is done by calling the delete on File object for that directory.

```java
boolean success = (new File("directoryName")).delete();
if (!success) {
    // Deletion failed
}
```

## Perl
Use rmtree function in File::Path module.

```perl
use File::Path 'rmtree';
rmtree([ "$dirName" ]);
```

## C
This is similar to previous section for processing files, except that here processing file is removing it and then removing the directory. To remove the file, its complete path is built.

```c
void removeDir(const char *name) {
	DIR *directory;
	struct dirent *dir_entry;
	char *buf;
	size_t len;

	directory = opendir(name);
	dir_entry = readdir(directory);
	size_t path_len = strlen(name);
	do {
    	        if (dir_entry->d_type == DT_DIR) {
        	                 char path[1024];
        	                 int len = snprintf(path, sizeof(path)-1, "%s/%s", name, dir_entry->d_name);
        	                 path[len] = 0;
        	                 if (strcmp(dir_entry->d_name, ".") == 0 || strcmp(dir_entry->d_name, "..") == 0)
            		continue;
        	                 removeDir(path);
    	        }  else {
    	                 len = path_len + strlen(dir_entry->d_name) + 2;
    	                buf = malloc(len);
    	                snprintf(buf, len, "%s/%s", name, dir_entry->d_name);
        	                unlink(buf);
                              }
	} while (dir_entry = readdir(directory));
	closedir(directory);
	rmdir(name);
}
```

## Bash

Use command rm to delete directory and its contents.

```c
rm -rf directory_to_be_deleted
```
