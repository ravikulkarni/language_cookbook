# Executing/Running any command

## Java

A good way to do this is using Runtime class. It is a good practice to clean out the streams from the process before exiting from the program. Example is given below is the class that can be used to read the streams from the Runtime

```java
class StreamReader extends Thread {
   InputStream is;
  String type
   StreamReader(InputStream is, String type) {
       this.is = is;
       this.type = type;
   }
   
   public void run() {
       try {
           InputStreamReader isr = new InputStreamReader(is);
           BufferedReader br = new BufferedReader(isr);
           String line=null;
           while ( (line = br.readLine()) != null) {
	//Do something with the line. May use type to differentiate between error and stdout stream
           }
                 
       } catch (IOException ioe){
               ioe.printStackTrace();  
       }
   }
}
```

The program to call these threads is given below.  The Process object is returned when the command is executed. The threads read the output and error stream from these process object.

```
String[] cmd;
//initialize cmd array.
Runtime rt = Runtime.getRuntime();
Process proc = rt.exec(cmd);
StreamReader errorStreamReader = new StreamReader(proc.getErrorStream(), "ERROR");            
StreamReader outputStreamReader = new StreamReader(proc.getInputStream(), "OUTPUT");
errorStreamReader.start();
outputStreamReader.start();
int exitVal = proc.waitFor();
//Catch java.io.IOException and java.lang.InterruptedException
```

## Perl

There are 4 ways to do this
- using ‘system’ command if you do not want to capture its output
- using ‘exec’ command if you do not want to return to the calling perl script
- using backticks if you want to capture the output of the command. Output captured is STDOUT.
- using ‘open’ if you want to pipe the command (as input or output) to your script.

Examples of usages are given below

```perl
system("command", "arg1", "arg2", "arg3");

$result = `command arg1 arg2`;

open(PS,"ls -l |") || die "Failed: $!\n";
while ( <PS> )
{
 #-- do something here
}
```

## C

In C the system commands are best executed using execve command. Please refer to the command details for the return code value.
Example below shows usage of the command.

```c
//Include unistd.h
int ret;
char *envp[] = { NULL };
char *argv[] = { "/bin/ls", "-l", NULL }
if(execve(argv[0], argv, envp) == -1) {
   perror("Error executing ls");
   _exit(127);
}
```

The input is incorporated into the args array and passed as an argument to execve(). It must fork a new process before executing "/bin/ls" in the child process

## Bash

In bash terminal the command is run by calling it.
