# Variables

## Getting environment variables

### Java
There is a method in System class called getEnv that returns all the environment in form of Map object. The object can be iterated over to get the key and values

Example of that is below. The environment variable that is read is PATH.

```java
Map<String, String> env = System.getenv();
String pathValue = env.get(“PATH”);
```

### Perl
In Perl the environment variables are stored in special hash named %ENV. To access particular environment variable, use that environment variable as key of that hash. Following can be used as an example to get the PATH variable.

```perl
$userName =  $ENV{'PATH'};
```

### C

There is a function named getenv declared in stdlib.h that can be used to get the environment variables
```c
char * pPath = getenv ("PATH");
```

### Bash

Getting the environment variable for bash is probably the easiest

Just use the variable like below
```bash
echo $PATH
```

## Setting environment variables

### Java
In Java when the VM starts it makes a copy of the environment variable. There is no function to write the environment variable in the same process as the VM

### Perl
In perl for the current running process the environment variable can be set just by simply manipulating %ENV hash. In example below, the environment variable PATH is updated to a new value.

```perl
$ENV{‘PATH’} = “new Path”;
```

### C
In C this can be done using putenv method as shown below. The environment PATH is modified in the example below.

```c
putenv("PATH=C:\");
```

### Bash

In Bash, this is also one of the easy to do. Just set the environment variable as shown below.

```bash
PATH = “C:\”
```
