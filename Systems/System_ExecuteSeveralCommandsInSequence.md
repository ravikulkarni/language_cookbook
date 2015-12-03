# Running several commands in Sequence

## Java
To run multiple commands you can put all those commands into a .sh file and invoke the code in above section to run those commands.  Alternatively you can call exec commands on each of the command while making sure that the output and error streams are read before calling next exec command.

## Perl
Use one of the calls in the section above. Just seperate commands with “;”

## C
To run multiple commands you can put all those commands into a .sh file and invoke the code in above section to run those commands.  Alternatively you can call execve commands on each of the command one after another.

## Bash
The commands can be run one after another by separating them with “;” .

