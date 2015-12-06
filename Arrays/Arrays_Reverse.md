# Reversing array

## Java

If the array is of primitive data type, then example below shows how you can reverse the array.

```java
int []array1 = {1,2,3,4,5};
int left = 0;
int right = array1.length - 1;

while( left < right ) {
   int temp = array1[left];
   array1[left] = array1[right];
   array1[right] = temp;
   left++;
   right--;
}
```

If the array is of Object type then it can be reversed as given below

```java
Integer []array1;
//Populate array1 with Integer data
List  list = Arrays.asList(array1);
Collections.reverse(list);
Integer [] reversed =  (Integer[])list.toArray();
```

## Perl

In Perl this can be easily done by using "reverse" function
Below is an example

```perl
my @array = (0,1,2,3,4,5,6);
my @reverseArray = reverse(@array);
```

## C

The C function for doing this could be on same lines as for java array of primitive type. Example just like above is

```c
int array1[5] = {1,2,3,4,5};
int left = 0;
int right = sizeof(array1)/sizeof(int) - 1;

while( left < right ) {
   int temp = array1[left];
   array1[left] = array1[right];
   array1[right] = temp;
   left++;
   right--;
}
```

## Bash

In Bash this has to be done by using another array, reading first array in reverse order and storing it in new array. Example of this is given below

```bash
a1=(one two three four)
r=0
for (( i=${#a1[@]}; i>=0; i-- ));
do
    f[$r]=${a1[$i]}
    ((r++))
done
```



