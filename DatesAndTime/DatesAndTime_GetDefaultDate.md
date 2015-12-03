# Getting default dates

## Java

In Java the GregorianCalendar class is to be used. This is the class that implements the calendar that we use. There are various fields that give information about the date.

```java
Calendar cal = new GregorianCalendar();

// Get the components of the date
int era = cal.get(Calendar.ERA);               // 0=BC, 1=AD
int year = cal.get(Calendar.YEAR);             // 2012
int month = cal.get(Calendar.MONTH);           // 0=Jan, 1=Feb, ...
int day = cal.get(Calendar.DAY_OF_MONTH);      // 1...
int dayOfWeek = cal.get(Calendar.DAY_OF_WEEK); // 1=Sunday, 2=Monday, ...
```

## Perl

In Perl the call to localtime returns array of different parameters of date like seconds, minutes etc.
The year value is after 1900. Also the day of the week value starts from 0 with value of 0 for Sunday. Similarly the value of month is also 0 based with 0 for January.

```perl
@months = qw(Jan Feb Mar Apr May Jun Jul Aug Sep Oct Nov Dec);
@weekDays = qw(Sun Mon Tue Wed Thu Fri Sat Sun);

($second, $minute, $hour, $dayOfMonth, $month, $yearOffset, $dayOfWeek, $dayOfYear, $daylightSavings) = localtime();

$year = 1900 + $yearOffset;
$theTime = "$hour:$minute:$second, $weekDays[$dayOfWeek] $months[$month] $dayOfMonth, $year";
print $theTime;
```

## C
With C, you get the current time using time function. The time_ value which is the epoch seconds after 1900 when passed to localtime function returns a time structure with the values for year, month etc set.

```c
  time_t currentTime = time(NULL);
  struct tm *aTime = localtime(&currentTime);

  int day = aTime->tm_mday;
  int month = aTime->tm_mon + 1;
  int year = aTime->tm_year + 1900; 

  printf("%d %d %d\n", day, month, year);
```

## Bash
With Bash the command ```date``` will give the date information
