# Finding your own IP address.

## Java
First use InetAddress to get the localhost InetAddress and then use getAddress method to get the 4 byte array with the IP address. This will give the IP addresses if there are more than one.

```java
try {
   InetAddress addr[] = InetAddress.getAllByName(“localhost”);

   // Get IP Address
  for(int i = 0; i<addr.length; i++) {
   	byte[] ipAddr = addr[i].getAddress();
	//Do something with the InetAddress
  }

} catch (UnknownHostException e) {
}
```

## Perl

With Perl most of the network programming can be done by IO::Socket module. In the example below inet_ntoa would take the packed data returned by gethostbyname and convert it into a string

```perl
use IO::Socket;
my($addr)=inet_ntoa((gethostbyname("hostname"))[4]);
print "$addr\n";
```

## C

The network addresses in the host can be found out by using getifaddrs function (to get the interfaces into a array of structures), getnameinfo (to get the address and interface name) . The family of the interface should be of type AF_INET

```c
struct ifaddrs *ifaddr, *ifa;
  int family, s;
  char host[NI_MAXHOST];
  
  if (getifaddrs(&ifaddr) == -1) {
    perror("getifaddrs");
    exit(EXIT_FAILURE);
  }
  
  for (ifa = ifaddr; ifa != NULL; ifa = ifa->ifa_next) {
    family = ifa->ifa_addr->sa_family;
    
    if (family == AF_INET) {
      s = getnameinfo(ifa->ifa_addr, sizeof(struct sockaddr_in),
		      host, NI_MAXHOST, NULL, 0, NI_NUMERICHOST);
      if (s != 0) {
	printf("getnameinfo() failed: %s\n", gai_strerror(s));
	exit(EXIT_FAILURE);
      }
      printf("<Interface>: %s \t <Address> %s\n", ifa->ifa_name, host);
    }
  }
```

## Bash
Use command below

```bash
/sbin/ifconfig | grep “inet addr” | cut -d’:’ -f2 | awk ‘{print $1}’
```
Grep filters only strings with ‘inet addr’ in it. The next cut statement removes the left hand part of string.  

