# Inverting hash

## Java
With Java there are no ready methods to invert the hash. Therefore it has to be done something like below

```java
HashMap hashMap1 = new HashMap();
hashMap1.put(“key1”, 5);
hashMap1.put(“key2”, 4);
hashMap1.put(“key3”, 3);
hashMap1.put(“key4”, 2);
Map inv = new HashMap();
Set set = hashMap1.entrySet();
Iterator i = set.iterator();
while(i.hasNext()) {
   Map.Entry entry = (Map.Entry)i.next();
   inv.put(entry.getValue(), entry.getKey());
}
```

## Perl
Inverting of hash means to swap the keys and values. The values now become keys.and the keys are values. This is useful when you want to find the keys if you know the values. To do this “reverse” function is used..

Example is given below

```perl
%hash1 = (‘key1’ => ‘value1’,
    ‘key2’ => ‘value2’,
    );

%valueHash1 = reverse %hash1;
```

## C
There is no inbuilt function for inverting array in libcfu. The inverting logic has to be built using the available functions.

## Bash
The inverting of associative array has to be done using looping constructs as given below

```bash
declare -A cities=( ["us"]="boston" ["canada"]="toronto" ["france"]="paris" ["England"]="london" )
declare -A invCities = ()
for k in "${!cities[@]}"
do
	invCities[${cities["$k"]}] = $k
done
```
