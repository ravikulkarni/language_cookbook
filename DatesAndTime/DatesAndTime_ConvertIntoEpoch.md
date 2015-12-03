# Converting dates and times into epoch seconds

## Java

The epoch seconds can be obtained from Gregorian Calendar by calling getTime() which returns the Date object and again calling getTime() on the Date Object to get the epoch. The epoch value is in milliseconds here.

```java
long epochSec = new GregorianCalendar().getTime().getTime();
```

The above example creates Calendar with current time. However you could create GregorianCalendar object with any specific date.

## Perl

With Perl it is easy to use DateTime module. An example below shows how to get the epoch seconds.

```perl
use DateTime;
$dt = DateTime->new( year => 2012, month => 07, day => 16, hour => 11, minute => 30,
   	second => 0, nanosecond => 500000000, time_zone => 'local' );
$epoch_time = $dt->epoch;
```

## C

With C you have to set the values in the structure “tm” and then call mktime to create the value of epoch seconds after 1900. An example is given below.

```c
 struct tm  stime;
  time_t time;

  stime.tm_year = 2013-1900;
  stime.tm_mon = 1;
  stime.tm_mday = 1;
  stime.tm_hour = 8;
  stime.tm_min = 0;
  stime.tm_sec = 0;
  stime.tm_isdst = 0;
  
  time_of_day = mktime(&stime);
  printf("%lu\n",time);
```

## Bash
To get the epoch seconds just use the date command as given below

```bash
date ‘+%s’
```
