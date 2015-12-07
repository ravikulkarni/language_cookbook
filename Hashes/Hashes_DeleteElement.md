# Deleting element from hash

## Java
The API to delete the key, value pair in the hash is “remove”. The return value of the “remove” call is either a null or the old value associated with the key “key1”. If the value is null, it means either the old value of the key  “key1” is null or there was no key “key1” in the hash.

```java
HashMap hashMap = new HashMap();
hashMap.put(“key1”, “value1”);
hashMap.put(“key2”, “value2”);
hashMap.remove(“key1”);
```

## Perl
In Perl the elements (key, value pair) is deleted  by calling delete command. Example given above for the hash1 and hash1Ref

```perl
delete $hash1{‘key1’};

delete $hash1Ref->{‘key1’};
```

## C

The “cfuhash_delete” is the function used to delete a particular key from the hash.

```c
cfuhash_table_t *hash = cfuhash_new_with_initial_size(10);
cfuhash_put(hash, "key1", "value1");
cfuhash_put(hash, "key2", "value2");
cfuhash_put(hash, "key3", "value3");
cfuhash_put(hash, "key4", "value4");
cfuhash_delete(hash, "key4");
```

## Bash
In Bash the element in associative array can be deleted using “unset” call

```bash
declare -A cities=( ["us"]="boston" ["canada"]="toronto" ["france"]="paris" ["England"]="london" )
unset cities[“canada”] # deletes the canada key and value from the cities associative array
```
