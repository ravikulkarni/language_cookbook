# Finding current working directory

## Java

Use getProperty of System class to get “user.dir“ property which will give current working directory

```java
String curDir = System.getProperty("user.dir");
```

## Perl
Use`pwd` to get the current working directory.

```perl
my $abs_path = `pwd`;
```

## C

Use call getcwd to get the current working directory

```c
char *cwd;
     	if ((cwd = getcwd(NULL, 64)) == NULL) {
   	  //deal with the error
     	}
     	printf("%s\n", cwd);
     	free(cwd); /* free memory allocated by getcwd() */
```

## Bash
Use ```pwd``` command to return the present working directory
