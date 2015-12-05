# Making numbers even more random

## Java

The numbers can be made more random and secure using SecureRandom class

```java
SecureRandom random = new SecureRandom();
byte bytes[] = new byte[20];
random.nextBytes(bytes);
```
The SecureRandom class also has methods from Random class to get random numbers of different types.

SecureRandom class instance can also be created using getInstance method passing algorithm and provider.

For example

```java
SecureRandom prng = SecureRandom.getInstance("SHA1PRNG");
```

Here need to catch exception java.security.NoSuchAlgorithmException

## Perl
This can be done using modules from CPAN

```perl
use Math::TrulyRandom;
$random = truly_random_value();
```

## C
The random numbers can be made more random by setting seed with srand. The seed value could be generated from time.

```c
time_t sec;
time(&sec);
srand ( sec );
int randomNo = rand();
```

## Bash
A better way to generate random numbers is to use /dev/urandom. Below is an example of generating random numbers from 0 to $max

```bash
newRand=$[ ( `cat /dev/urandom|od -N1 -An -i` % ( $[ $highest - $lowest ] )) + $lowest ]
```
