# Iterating over hash

## Java

For iterating over the hash in Java, any looping construct can be used.However java provides an function that returns keys in a form of Set class. The Set class has Iterator interface implemented for iterating over the keys. It is done as shown below

```java
HashMap hashMap = new HashMap();
hashMap.put(“key1”, “value1”);
hashMap.put(“key2”, “value2”);
hashMap.put(“key3”, “value3”);
hashMap.put(“key4”, “value4”);
Set keySet = hashMap.keySet();
Iterator it = keySet.iterator();
while(it.hasNext()){
	// Do something with (String)it.next()
}
```

## Perl
In perl the hash can be iterated over using any of the looping constructs. The keys to be used are returned using ’keys’ keyword.
Below is an example of iterating over hash using for loop. Hash and its reference defined in the section above are used

```perl
for (keys %hash1) {
        #Do something with $hash1{$_};
}
```

For has reference you have to first dereference is using % before you could used “keys” operator on it.

```perl
for (keys %$hash1Ref) {
        #Do something with $hash1Ref->{$_};
}
```

## C

The libcfu library has  a function ```cfuhash_keys_data``` defined which returns the keys from the hash.

Returns all the keys from the hash.  The number of keys is placed into the value pointed to by num_keys.  If key_sizes is not NULL,  it will be set to an array of key sizes.  If fast is zero, copies of the keys are returned.  Otherwise, pointers to the real keys will be returned.

```c
void **cfuhash_keys_data(cfuhash_table_t *ht, size_t *num_keys, size_t **key_sizes, int fast);
```

The keys returned are then used to extract the value from the hash using “cfuhash_get” function.

```c
void *cfuhash_get(cfuhash_table_t *ht, const char *key);
```

An example below shows it usage

```c
cfuhash_table_t *hash = cfuhash_new_with_initial_size(10);
cfuhash_put(hash, "key1", "value1");
cfuhash_put(hash, "key2", "value2");
cfuhash_put(hash, "key3", "value3");
cfuhash_put(hash, "key4", "value4");

char **keys = NULL;
size_t *key_sizes = NULL;
size_t key_count = 0;
  	
keys = (char **)cfuhash_keys_data(hash, &key_count, &key_sizes, 0);

printf("\n\nkeys (%u):\n", key_count);
for (i = 0; i < key_count; i++) {
  printf("%s => %s\n", keys[i], (char *)cfuhash_get(hash, keys[i]));
  free(keys[i]);
}
free(keys);
free(key_sizes);
```

## Bash

In Bash for example, if the code below is the array,

```bash
declare -A cities=( [‘’us”]=”boston” [“canada”]=”toronto” [“france”]=”paris” [“England”]=”london” )
```

Then the following expression evaluates into all indexes of the associative array:

```bash
“${!cities[@]}”
```

Code below shows how to iterate with bash array.

```bash
for country in “${cities[@]}” do
# Do something with $country and ${cities[$country]}
done
```
