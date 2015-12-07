# Sorting hash

## Java

In Java there is a class which guarantees that the keys are in sorted manner. The sorting is either done by natural order or via Comparator class provided. Using this feature of Java, the HashMap can be sorted with either keys or values
Example is given below shows how to sort array using values

```java
public static void main(String[] args) {
	HashMap hashMap = new HashMap();
	hashMap.put(“key1”, 5);
	hashMap.put(“key2”, 4);
	hashMap.put(“key3”, 3);
	hashMap.put(“key4”, 2);
           HashValueComparator comp =  new HashValueComparator(hashMap);
           TreeMap sortedHashMap = new TreeMap(comp);
           sortedHashMap.putAll(hashMap);
}

class HashValueComparator implements Comparator {
 Map base;
 public HashValueComparator(Map base) {
     this.base = base;
 }
 public int compare(Object a, Object b) {

   if((Integer)base.get(a) < (Integer)base.get(b)) {
     return -1;
   } else if((Integer)base.get(a) == (Integer)base.get(b)) {
     return 0;
   } else {
     return 1;
   }
 }
}
```

In above example, if we do not use HashValueComparator, then the sorting happens on keys.

```java
public static void main(String[] args) {
HashMap hashMap = new HashMap();
hashMap.put(“key1”, 5);
	hashMap.put(“key2”, 4);
	hashMap.put(“key3”, 3);
	hashMap.put(“key4”, 2);
       	TreeMap sortedHashMap = new TreeMap();

	
	

       	sortedHashMap.putAll(hashMap);
}
```

## Perl
The hash can be either sorted by keys or by values.
For the hashes defined in sections above, sorting by keys is done as given in examples below

```perl
foreach $key (sort keys %hash1) {
    # Do something with sorted $keys and $hash1{$key}
}

foreach $key (sort keys %$hash1Ref) {
    # Do something with sorted $keys and $hash1Ref->{$key}
}
```

In the examples above ```sort``` function sorts the array returned by keys.

Sorting by values is done as below. Here again sort function is used and passed in a block that tells how the sorting is to be done and what values are to be used for sorting.

```perl
foreach $value (sort {$hash1{$a} cmp $hash1{$b} } keys %hash1) {
    # Do something with the sorted values
}

foreach $value (sort {$hash1Ref->{$a} cmp $hash1Ref->{$b} } keys %$hash1Ref) {
    # Do something with the sorted values
}
```

## C
This involves creating a new hash for storing sorted hash. Take all the keys from original hash, sort them by sorting techniques as mentioned in other sections. Construct the output hash by reading sorted keys and their values from unsorted hash.

## Bash

The hash can be sorted by using sort function. The sort function is given an position to use for sorting using -k option

The example below sorts based on the key

```bash
declare -A cities=( ["us"]="boston" ["canada"]="toronto" ["france"]="paris" ["England"]="london" )
for k in "${!cities[@]}"
do
	echo $k ' - ' ${cities["$k"]}
done |
sort -k1
```

The example below sorts based on the value

```bash
for k in "${!cities[@]}"
do
	echo $k ' - ' ${cities["$k"]}
done |
sort -k3
```
