# Formatting dates

## Java

Use SimpleDateFormat as given in the example below

Letter	Date or Time Component	Presentation	Examples
G	Era designator	Text	AD
y	Year	Year	1996; 96
M	Month in year	Month	July; Jul; 07
w	Week in year	Number	27
W	Week in month	Number	2
D	Day in year	Number	189
d	Day in month	Number	10
F	Day of week in month	Number	2
E	Day in week	Text	Tuesday; Tue
a	Am/pm marker	Text	PM
H	Hour in day (0-23)	Number	0
k	Hour in day (1-24)	Number	24
K	Hour in am/pm (0-11)	Number	0
h	Hour in am/pm (1-12)	Number	12
m	Minute in hour	Number	30
s	Second in minute	Number	55
S	Millisecond	Number	978
z	Time zone	General time zone	Pacific Standard Time; PST; GMT-08:00
Z	Time zone	RFC 822 time zone	-0800

```java
String s;
Format formatter;
Date date = new GregorianCalendar().getTime();

 // 07/15/12
formatter = new SimpleDateFormat("MM/dd/yy");
s = formatter.format(date);

 // 2012.07.15.08.02.23
formatter = new SimpleDateFormat("yyyy.MM.dd.HH.mm.ss");
s = formatter.format(date);
```

## Perl
Use the fomat calendar call from DateTime module as given below

```perl
print DateTime->today->format_cldr('dd/MM/YYYY');
```

## C

Use strftime function as below to print time with different format.

```c
size_t strftime (char* ptr, size_t maxsize, const char* format,
                 const struct tm* timeptr );
```

The function fills the character array pointed to by argument with at most maxsize characters. The format string is used to format the time represented in the structure pointed to timeptr. Characters in the format string (including the terminating null) are copied unchanged into the array, unless one of the following format directives is found—then the value specified below is copied into the destination, as appropriate to the locale.

Example is below

```c
time_t rawtime;
struct tm * timeinfo;
char buffer [80];

time (&rawtime);
timeinfo = localtime (&rawtime);

strftime (buffer,80,"Current Time is  %I:%M%p.",timeinfo);
printf("%s", buffer);
```

* %a => abbreviated weekday name                               
* %A => full weekday name                                      
* %b => abbreviated month name                                 
* %B => full month name                                        
* %c => date and time representation                           
* %d => decimal day of month number 01–31                      
* %H => hour 00–23 (24 hour format)                            
* %I => hour 01–12 (12 hour format)                            
* %j => day of year 001–366                                    
* %m => month 01–12                                            
* %M => minute 00–59                                           
* %p => local equivalent of ‘AM’ or ‘PM’                       
* %S => second 00–61                                           
* %U => week number in year 00–53 (Sunday is first day of week 
* %w => weekday, 0–6 (Sunday is 0)                             
* %W => week number in year 00–53 (Monday is first day of week 
* %x => local date representation                              
* %X => local time representation                              
* %y => year without century prefix 00–99                      
* %Y => year with century prefix                               
* %Z => timezone name, or no characters if no timezone exists  
* %% => a % character                                          

The total number of characters copied into *s is 

## Bash

Use date command with strftime format specification

```bash
date ‘+%Y-%m-%d %H:%M:%S %Z’
#2012-07-17 10:33:12 EDT
```

Please refer to the documentation for the format specifiers.

