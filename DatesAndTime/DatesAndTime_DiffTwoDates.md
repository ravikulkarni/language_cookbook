# Difference of two dates.

## Java

The difference can be calculated by converting them into epoch seconds and taking the difference.

```java
Date date1 = new GregorianCalendar().getTime();

Calendar c2 = new GregorianCalendar();
c2.add(Calendar.MONTH, -2);
Date date2 = c2.getTime();

long difference = date1.getTime() - date2.getTime();
```
The difference above is in milliseconds which can be used to compute min, hours etc

## Perl

The date format is commonly used in MySQL hence use of that formatter. The logic is same here - compute duration difference

```perl
use DateTime;
use DateTime::Format::MySQL;
use DateTime::Format::Duration;

my $date = "2012-07-01 00:00:00";

my $dt1 = DateTime->now(time_zone => 'floating', formatter => 'DateTime::Format::MySQL');
my $dt2 = DateTime::Format::MySQL->parse_datetime($date);

my $duration = $dt1 - $dt2;
my $format = DateTime::Format::Duration->new(
   pattern => '%Y years, %m months, %e days, %H hours, %M minutes, %S seconds'
);
print $format->format_duration($duration);
```

## C
The C has a difftime function which calculates difference between 2 time_t values in seconds.
 An example below calculates diff in seconds between now and next month.

```c
time_t currentTime;
struct tm nextMonthTime;
double secs;
time(&currentTime);  
nextMonthTime = *localtime(&currentTime);
nextMonthTime.tm_mon = nextMonthTime.tm_mon + 1;
secs = difftime(mktime(&nextMonthTime),currentTime);
printf ("%.f seconds between now and next month.\n", secs);
```

## Bash

In Bash, just like in above sections , a good way to do the arithmetic with dates is by converting them into epoch, either adding or subtracting necessary seconds from epoch

```bash
date1=’2012-01-01 00:00:00’
epoch1=$(date -d “$date1” ‘+%s’)

epoch2=$(date -d “now” ‘+%s’)

difference=$((epoch2 - epoch1))

date2=$(date -d “1970-01-01 UTC $epoch2 seconds”)
```
