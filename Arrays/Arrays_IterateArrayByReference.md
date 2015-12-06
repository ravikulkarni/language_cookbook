# Iterating over array by reference

## Java
In Java there are no special ways to handle array references. The array if passed to a method are passed by reference instead of passing as reference by value. Within the method, handling of array is no different.

## Perl
This is done by first de referencing array referencee to array and then using the foreach command.

```perl
my @array = (0,1,2,3,4,5,6);
my $arrReference = \@array;
foreach my $arrayElement (@$arrReference) {
# Do something with $arrayElement
}
```

You can also use array reference as below

```perl
for (my $i = 0; $i <= $#$arrReference; $i++) {
   # do something with $arrReference->[$i]
}
```

## C
In C the array can also be accessed in form of pointers. Adding numbers consecutively will give the subsequent elements in the array. Example is given below

```c
int a1[5] = { 1, 2, 3, 4, 5 };
```

Here ```*a1``` will give value of ```1```;
Similarly ```*(a1+1)``` will give value of ```2```

## Bash

In bash the arrays cannot be accessed by references.

