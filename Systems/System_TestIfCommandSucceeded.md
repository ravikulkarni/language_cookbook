# Telling if command succeeded or not.

## Java
Refer to above section. The waitFor call returns 0 if the command succeeded

## Perl
In perl the command failure can be checked if $? is equal  to -1

## C
After running the command as in previous section the return value tells the success or failure of the command. If a command is not found, the exit status shall be 127. If the command name is found, but it is not an executable utility, the exit status shall be 126. Applications that invoke utilities without using the shell should use these exit status values to report similar errors.

## Bash
Just like in perl the command failure can be checked if $? not equal to 0
