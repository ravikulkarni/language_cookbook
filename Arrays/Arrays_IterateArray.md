# Array iteration

## Java
There are more than one ways to do that depending on what your array is. For the array defined using new operator, you could use any of the looping constructs. Example below gives one way to iterate over those elements

```java
int []a = new int[2] ;
a[0] = 0;
a[1] = 1;
for(int i=0;i<a.length;i++){
	//Do something with a[i];
}
```

While you can use any of the looping constructs for ArrayList, better appoach is using Iterator. Example of both is given below

```java
List strList = new ArrayList();
strList.add(“String1”);
strList.add(“String2”);

for(int i=0;i<strList.size();i++){
	//Do something with strList.get(i);
}

Iterator it = strList.iterator();
while(it.hasNext()){
    String s = (String)it.next();
}
```

Use of Generics will allow not casting the Object returned by it.next() to String.

## Perl
Using foreach is the easiest way to iterate over elements of array
Example is given below

```perl
my @array = (0,1,2,3,4,5,6);
foreach my $arrayElement (@array) {
# Do something with $arrayElement
}
```

## C
Iterating array in C is much like in Java. Example is given below

```c
int a1[5] = {1,2,3,4,5};
int i=0;
int array_size = sizeof(a1)/sizeof(int);
for(i=0;i< array_size; i++) {
	// Do something with a1[i]
}
```

## Bash
In Bash for example, if the code below is the array,

```bash
cities=( boston canada paris london )
```

Then the following expression evaluates into all values of the array:

```bash
${cities[@]}
```

Code below shows how to iterate with bash array.

```bash
for name in ${cities[@]}
do
# other stuff on $name
done
```

On side note the arrays expansion expression can be written one of 4 possible ways.

```bash
${cities[@]}
“${cities[@]}”
${cities[*]}
“${cities[*]}”
```
For the unquoted expression with ```*``` and ```@``` expand to same set. For the quoted expression, ```@``` expands to all elements individually quoted, * expands to all elements quoted as a whole.
