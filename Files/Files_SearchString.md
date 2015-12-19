# Searching for a string in a file

## Java

The Scanner class in the java.util package simplified lot of things related to parsing of a text in a file
An example given below shows how to use that. Here f is the file to read and searchString is the string to be searched.

```java
boolean result = false;
try {

   Scanner in = new Scanner(new FileReader(“somfile.txt”));
  boolean result = false;
   while(in.hasNextLine() && !result) {
      result = in.nextLine().indexOf(“searchString”) >= 0;
   }
   if(result) {
      //Do something when the string is found
   }
   in.close();
} catch(IOException e) {
   e.printStackTrace();      
}
```

## Perl

One  of the way to do this in perl is to use its inbuilt grep function on line to be searched

```perl
open(F,"fileToBeSearched.txt");
@list=<F>;
close F;
$this="String to be searched";
@f=grep /$this/,@list;
if(scalar @f) {
	#Do something when the string is found
}
```

## C

In C use strstr function to check if the substring is present
An example below shows the code

```c
FILE *fp=fopen(“filetobesearched.txt”,"r");
char  tmp[256]={0x0};
while(fp!=NULL && fgets(tmp, sizeof(tmp),fp)!=NULL){
   if (strstr(tmp, “stringToBeSearched”)) {
	/*Do something when string is found*/
	break;
   }    
}
if(fp!=NULL) fclose(fp);
```

## Bash

In Bash, this is done by simple use of egrep command which takes regular expression as argument for string to be searched.

```bash
count=`egrep -ic "string" "file.txt"`

if [ $count -gt 0 ]
then
    echo found
fi
```
