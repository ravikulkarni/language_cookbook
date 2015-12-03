# Converting epoch seconds into dates and times.

## Java

Here create a GregorianCalendar object with current time and then set its time to Date created using epoch seconds.

```java
Calendar cal = new GregorianCalendar().setTime(new Date(epochSec));
```

## Perl

Use from_epoch to create DateTime object from epoch seconds.

```perl
use DateTime;
$dt = DateTime->from_epoch( epoch => $epoch );
$year = $dt->year;
$month = $dt->month; # 1-12 - you can also use '$dt->mon'
$day = $dt->day; # 1-31 - also 'day_of_month', 'mday'
$dow = $dt->day_of_week; # 1-7 (Monday is 1) - also 'dow', 'wday'
$hour = $dt->hour; # 0-23
$minute = $dt->minute; # 0-59 - also 'min'
$second = $dt->second; # 0-61 (leap seconds!) - also 'sec'
$doy = $dt->day_of_year; # 1-366 (leap years) - also 'doy'
$doq = $dt->day_of_quarter; # 1.. - also 'doq'
$qtr = $dt->quarter; # 1-4
$ymd = $dt->ymd; # 2012-08-30
$ymd = $dt->ymd('/'); # 2012/08/30 - also 'date'
$hms = $dt->hms; # 13:30:00
$hms = $dt->hms('|'); # 13|30|00 - also 'time'
```

## C
Use localtime to convert time_t value into time structure

```c
struct tm *newtime;
  char am_pm[] = "AM";
  time_t long_time=1229521513;
  
  newtime = localtime(&long_time);
  if(newtime->tm_hour>12)
    strcpy(am_pm,"PM");
  if(newtime->tm_hour>12)
    newtime->tm_hour-=12;
  if(newtime->tm_hour ==0)
    newtime->tm_hour=12;
  
  printf("%.19s %s, %i\n", asctime(newtime),am_pm, 1900+newtime->tm_year);
```

## Bash

Use date command  with -d option to give the date from epoch seconds

```bash
epoch=’1234567890’
date -d “1970-01-01 UTC $epoch seconds”  “+%Y-%m-%d %T %z”
```
