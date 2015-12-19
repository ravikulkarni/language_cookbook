# Removing duplicate lines

## Java

The example below uses Set data structure in java to remove duplicate files. This should work for reasonably large sized files

```java
try{
BufferedReader reader = new BufferedReader(new FileReader(“inputfile.txt”));
Set<String> lines = new HashSet<String>(10000);
String line;
while ((line = reader.readLine()) != null) {
   lines.add(line);
}
reader.close();
BufferedWriter writer = new BufferedWriter(new FileWriter(“outputfile.txt”));
for (String unique : lines) {
   writer.write(unique);
   writer.newLine();
}
writer.close();
  } catch (IOException e){
	//Do something  for exception.
 }
```

## Perl

Below is an example of removing duplicate files. The code below prints out the lines whenever it is seen only once. Determining the number of occurences is done with help of %seen hash.

```perl
my $file =‘somefile.txt’;
my %seen = ();
open(FH, "<$file");
while(<FH>){
   $seen{$_}++;
   next if $seen{$_} > 1;
   print;
}
close FH;
```

## C
The only way to remove lines from a text file is to copy the file without those lines in the copy. 

## Bash
In bash you can use sort command and pass-u as an argument to return uniq lines from the file.
```bash
sort -u filename > filename.new
```
