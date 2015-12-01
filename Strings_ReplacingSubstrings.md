# Replacing substrings

## Java
String class has overloaded functions to replace the characters. The signature of the methods is self explanatory.

```java
replaceAll(String regex, String replacement)
replaceFirst(String regex, String replacement)
replace(char oldChar, char newChar)
```

The replaceAll and replaceFirst throws PatternSyntaxException if the regular expression's syntax is invalid.

```java
String str = “Today is a sunny day”;
String replacedString = str.replaceAll(“sunny”, “rainy”);
```

## Perl

The easiest way to do this in Perl is using Regular Expressions substitution statement.

```perl
my $str = “Today is a sunny day”;
$str =~ s/sunny/rainy/g;  #This will make $str as “Today is a rainy day”.
```

Here g is option to indicate that make this replacement global

## C

In C there is no ready function available to do the string replacement. Instead a sample below could do the task. The method below first finds out how many times the pattern occurs. Then based on that count, memory for the new string is allocated. Then the patterns are replaced with the new pattern.

```c
char * replace( char const * const original, char const * const pattern, char const * const replacement ) {
 size_t const replen = strlen(replacement);
 size_t const patlen = strlen(pattern);
 size_t const orilen = strlen(original);

 size_t patcnt = 0;
 const char * oriptr;
 const char * patloc;

 // find how many times the pattern occurs in the original string
 for (oriptr = original; patloc = strstr(oriptr, pattern); oriptr = patloc + patlen)  {
   patcnt++;
 }


 // allocate memory for the new string
 size_t const retlen = orilen + patcnt * (replen - patlen);
 char * const returned = (char *) malloc( sizeof(char) * (retlen + 1) );

 if (returned != NULL)  {
   // copy the original string,
   // replacing all the instances of the pattern
   char * retptr = returned;
   for (oriptr = original; patloc = strstr(oriptr, pattern); oriptr = patloc + patlen) {
     size_t const skplen = patloc - oriptr;
     // copy the section until the occurence of the pattern
     strncpy(retptr, oriptr, skplen);
     retptr += skplen;
     // copy the replacement
     strncpy(retptr, replacement, replen);
     retptr += replen;
   }
   // copy the rest of the string.
   strcpy(retptr, oriptr);
 }
 return returned;

}
```

## Bash

This can be done using either ${string/substring/replacement} or ${string//substring/replacement}. The difference between the two is that the former replaces only the first occurrence and the latter replaces all occurrence.

```bash
stringB = “Today is a sunny day”;
echo ${stringB//sunny/rainy}
```
