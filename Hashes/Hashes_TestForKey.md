# Testing for presence of key in hash

## Java

In HashMap class of Java there is a function “containsKey” that can be used to check if the key exists

```java
HashMap hashMap = new HashMap();
hashMap.put(“key1”, “value1”);
hashMap.put(“key2”, “value2”);
hashMap.put(“key3”, “value3”);
hashMap.put(“key4”, “value4”);
boolean key1Exists = hashMap.containsKey(“key1”);
```

Here key1Exists will return true.

## Perl
In Perl this is checked by using exists keyword. Example for the hashes defined above are

```perl
if(exists $hash1{‘key1’}) {
	# Do something when key1 exists
}

if(exists $hash1Ref->{‘key1’}) {
	# Do something when key1 exists
}
```

## C
Function ```cfuhash_exists``` is used to determine if the key exists.
The function definition is as below
```c
extern int cfuhash_exists(cfuhash_table_t *ht, const char *key);
```

The example below looks for key “key1” and “key10”

```c
cfuhash_table_t *hash = cfuhash_new_with_initial_size(10);
cfuhash_put(hash, "key1", "value1");
cfuhash_put(hash, "key2", "value2");
cfuhash_put(hash, "key3", "value3");
cfuhash_put(hash, "key4", "value4");
printf("key1 %s\n", cfuhash_exists(hash, "key1") ? "exists" : "does NOT exist!!!");
printf("key10 %s\n", cfuhash_exists(hash, "key10") ? "exists" : "does NOT exist!!!");
```

## Bash
In Bash the existence of key can be checked using if command as shown below

```bash
declare -A cities=( [‘’us”]=”boston” [“canada”]=”toronto” [“france”]=”paris” [“England”]=”london” )

us=”us”
africa=”africa”
if [[ ${cities[$us]} ]]; then echo "Exists"; fi   #It exists
if [[ ${cities[$africa]} ]]; then echo "Exists"; fi # It does not exist
```
