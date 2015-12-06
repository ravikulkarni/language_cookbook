# Extracting unique elements from a list

## Java
We follow approach same as for Perl. Instead of using Hash, add the elements to HashSet class. Example shown below. If the elements are primitive datatypes, then they can be autoboxed (converted into corresponding wrapper object) by adding them into ArrayList using “add” method

```java
List strList = new ArrayList();
strList.add(“String1”);
strList.add(“String2”);
strList.add(“String2”);
strList.add(“String3”);
strList.add(“String3”);
HashSet hs = new HashSet();
hs.addAll(strList);
strList.clear();
strList.addAll(hs);
```
Example to show autoboxing of primitive data type array for converting them into ArrayList object

```java
   int[] array1 = {0,1,2,3};
   ArrayList array1List = new ArrayList();
   for(int e : array1){
   	array1List.add(e);
   }
```

## Perl
A way to do this in perl is adding the array elements as key in hash. Then take all the keys of the hash and this will be unique elements from the array. Example is given below

```perl
undef %saw;
my @array = (0,1,2,5,3,4,4,5,6);
@saw{@array} = ();
@out = keys %saw;  
```

## C

In C the better approach to finding this is to sort the array first. Please refer to the subsequent section to see information about the sorting.
Once the array is sorted, following can be used to separate the unique elements of array.

```c
int a[10],b[10];
int i=0,j=0,k=0,n=0;
n = sizeof(a)/sizeof(int);
for(i=0,j=i+1;j<=n;j++) {
if(a[i]==a[j]) continue;
b[k++]=a[i];
i=j;
}
printf("The Unique elements in the array are \n");
for(i=0;i<k;i++)  {
printf("%d \n",b[i]);
}
```

Here the element is compared with the next element. If it is equal then the loop continues to pick following 2 numbers. If they are not equal they are copied on the array b and then the counters are moved accordingly

## Bash
In Bash this can be easily done using combination of sort and uniq command. Example is given below

```bash
intArr=( 4 6 3 10 2 3 )
uniqArr=( $( echo ${intArr[@]} | sed 's/ /\n/g' | sort -n | uniq ) )
echo ${uniqArr[@]}
```
