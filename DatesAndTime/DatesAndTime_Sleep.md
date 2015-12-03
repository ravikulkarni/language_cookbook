# Sleep

## Java

Use the sleep from Thread class with milliseconds to sleep as an argument.

```java
try {
Thread.sleep(4000);
} catch (InterruptedException e){
	//Do something.
}
```

## Perl

Use sleep call and pass the time to sleep in seconds.
```perl
sleep EXPR.

sleep 30.
```

## C
Use sleep call with following signature

```c
unsigned int sleep (unsigned int seconds)
```

The sleep function waits for seconds or until a signal is delivered, whichever happens first.
It returns 0 if the interval is over.  It returns remaining time if there is a delivery of signal. 

## Bash

Just like above sections use sleep call
Syntax
     sleep [NUMBER [smhd]]...
Key:
  s  :  seconds (default)
  m  :  minutes
  h  :  hours
  d  :  days

```bash
sleep 10s
```
