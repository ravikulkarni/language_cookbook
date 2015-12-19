# Counting lines, words or characters in file

## Java

The program to do this in java takes into account logic below
* Read the lines one by one. Increment line count
* Add the lengeth of each line to the character count.
* Use the word separators (space, comma , semicolon, colon, fullstop) to separate words.
Increment the word count accordingly

```java
int charCount=0;
int wordCount=0;
int lineCount=0;
StringTokenizer st;
String s;
BufferedReader buf=new BufferedReader(new FileReader(“somefile.txt”));
while((s=buf.readLine())!=null) {
       lineCount++;
       st=new StringTokenizer(s," ,;:.");
       while(st.hasMoreTokens()) {
               wordCount++;
               s=st.nextToken();
               charCount+=s.length();
       }
}
buf.close();
```

## Perl
The sample perl program below reads the file line by line and updates the counts for lines, words and characters.

```perl
open(FILE, "<file.txt") or die "Could not open file: $!";
my ($lines, $words, $chars) = (0,0,0);

while (<FILE>) {
   $lines++;
   $chars += length($_);
   $words += scalar(split(/\s+/, $_));
}

print("lines=$lines words=$words chars=$chars\n");
```

## C

With C the sample program below is similar to the Perl version where based on what the character is, the counts are updated.

```c
FILE *fp=fopen(“filetobesearched.txt”,"r");
int c = 0;
int characters = 0;
int lines = 0;
int words= 0;
while((c = fgetc(fp)) != EOF) {
	characters++;
	if(c == '\n')
		lines++;
	if(c == ' ' || c == '\t') words++;
}
printf("Characters: %d\nLines: %d\nWords: %d\n", characters, lines, words);
```

## Bash

For word count the command is wc -w
For line count the command is wc -l
For character count the command is wc-m
