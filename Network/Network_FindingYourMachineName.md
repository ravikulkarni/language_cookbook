# Finding your own name of the machine.

## Java

Java’s InetAddress class has a method getHostName that returns string hostname.

```java
try {
   InetAddress addr = InetAddress.getLocalHost();

   // Get hostname
   String hostname = addr.getHostName();
} catch (UnknownHostException e) {
}
```

## Perl

Use uname to get the hostname as given in the example below

```perl
use POSIX qw(uname);
($kernel, $hostname, $release, $version, $hardware) = uname();
```

## C
Use gethostname or gethostbyname as shown below

```c
char hostname[256];
hostname[255] = '\0';
gethostname(hostname, 255);
printf("Hostname: %s\n", hostname);
struct hostent* h;
h = gethostbyname(hostname);
printf("h_name: %s\n", h->h_name);
```

## Bash

Use command ```hostname``` to get the host name.

