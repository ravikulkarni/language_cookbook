# Flushing output

## Java

In java a flush to disk can happen in variety of ways as below. Some of them happen on certain triggers.
* PrintWriters auto-flush (by default) when you write an end-of-line,
* Streams and buffers flush when you close them.
* There's flush when the buffer is full.
* There is also a flush() call in all OutputStream and Writer classes

## Perl
Perl normally buffers output so it doesn't make a system call for every bit of output. To get around this, you have to unbuffer the output filehandle. The $| is one of the per-filehandle special variables, so each filehandle has its own copy of its value.
An example shows how to use it with STDOUT handle

```perl
my $previous_default = select(STDOUT);  # save previous default
$|++;                                   # autoflush STDOUT
select($previous_default);              # restore previous default
```

## C
In C there are couple of ways to flush the buffer
If you want to flush the buffered output at another time, call fflush, which is declared in the header file stdio.h.

This function causes any buffered output on stream to be delivered to the file. If stream is a null pointer, then fflush causes buffered output on all open output streams to be flushed.

This function returns ```EOF``` if a write error occurs, or zero otherwise.

There is also another function fflush_unlocked (FILE *stream)
The fflush_unlocked function is equivalent to the fflush function except that it does not implicitly lock the stream.

There is another call ```flushlbf (void)```
The ```_flushlbf``` function flushes all line buffered streams currently opened.

This function is declared in the stdio_ext.h header.

## Bash

No option avaliable to do this in bash
