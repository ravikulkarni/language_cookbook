# Date and Time arithmetic

## Java

The Calendar object has function to add, set date to a specific values. An example to add and subtract the different components of date. An example is given below.

```java
Calendar calendar = new GregorianCalendar();
// add 1m 2d
calendar.add(Calendar.MONTH,1);
calendar.add(Calendar.DAY_OF_MONTH,2);

//Substract 2m
calendar.add(Calendar.MONTH,-2);

//Add 2 hours
calendar.add(Calendar.HOUR,2);
```

## Perl

Use DateTime module

Example given below. Use add and subtract methods to change the dates

```perl
use DateTime;
my $first = DateTime
               ->last_day_of_month( year => 2012, month => 7 )
               ->add( days => 1 )
               ->subtract( seconds => 1 );
```

## Bash
In Bash, the best way to do the arithmetic with dates is by converting them into epoch, either adding or subtracting necessary seconds from epoch and then converting it back into date.

```bash
date1=’2012-01-01 00:00:00’
epoch1=$(date -d “$date1” ‘+%s’)

epoch2=$((epoch1 + 604800))
date2=$(date -d “1970-01-01 UTC $epoch seconds”)
```
