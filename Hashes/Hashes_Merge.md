# Merging hash

## Java

Merging hashes in Java is easily done using putAll call. The HashMap interface implements Map Interface and the putAll call takes Map object as an argument

Example is below

```java
HashMap hashMap1 = new HashMap();
hashMap1.put(“key1”, 5);
hashMap1.put(“key2”, 4);

HashMap hashMap2 = new HashMap();
hashMap2.put(“key3”, 3);
hashMap2.put(“key4”, 2);

hashMap2.putAll(hashMap1);
```

The resultant hashMap2 will have all the 4 keys.

## Perl
Below is an example of how to merge 2 hashes.

```perl
%hash1 = (‘key1’ => ‘value1’,
    ‘key2’ => ‘value2’,
    );

%hash2 = (‘key3’ => ‘value3’,
    ‘key4’ => ‘value4’,
    );

%tmpHash = (%hash1, %hash2); %hash1 = %tmpHash;
```

Or

```perl
@hash1{keys %hash2} = values %hash2;
```

## C

The libcfu library provides a function to copy the source hash into destination hash. The function name is “cfuhash_copy”

```c
extern int cfuhash_copy(cfuhash_table_t *src, cfuhash_table_t *dst);

hash = cfuhash_new_with_initial_size(30);
cfuhash_put(hash, "key1", "value1");
cfuhash_put(hash, "key2", "value2");
   
cfuhash_put(hash2, "key3", "value3");
cfuhash_put(hash2, "key4", "value4");
cfuhash_copy(hash2, hash);
```

## Bash
Bash does not have an easier way to merge associative arrays like arrays. Therefore this has to be done using looping constructs

```bash
declare -A cities1=( ["us"]="boston" ["canada"]="toronto")
declare -A cities2=( ["france"]="paris" ["England"]="london" )

for k in "${!cities1[@]}"
do
	cities2[“$k”] = ${cities1["$k"]}
done
```
