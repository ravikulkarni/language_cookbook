# Adding element to hash

## Java
The API to add key and value pair to hash is ‘put’. The API is used as below

```java
HashMap hashMap = new HashMap();
hashMap.put(“key1”, “value1”);
```

The return value of the “put” call is either a null or the old value associated with the key “key1”. If the value is null, it means either the old value of the key  “key1” is null or there was no key “key1” in the hash.

## Perl
In Perl the adding an element to has is simply passing key and value as given below. If the key passed is not present in the hash, it gets added to the hash. Otherwise the value of that key is updated to the new value

Below are examples of how it is done for hash and hash references
```perl
%hash1 = (‘key1’ => ‘value1’,
    ‘key2’ => ‘value2’,
    ‘key3’ => ‘value3’
    );
$hash1{‘key4’} = ‘value4’;

$hash1Ref = {‘key1’ => ‘value1’,
       ‘key2’ => ‘value2’,
       ‘key3’ => ‘value3’
      };
$hash1ref->{‘key4’} = ‘value4’;
```

## C

With libcfu, the elements can be added to the hash using “cfuhash_put”. Example is given below

```c
cfuhash_table_t *hash = cfuhash_new_with_initial_size(10);
cfuhash_put(hash, "key1", "value1");
cfuhash_put(hash, "key2", "value2");
cfuhash_put(hash, "key3", "value3");
cfuhash_put(hash, "key4", "value4");
```

## Bash
The values in the associative array with string indices are set as below.

```bash
declare -A hash1
hash1[“key1”] = “value1”
hash1[“key2”] = “value2”
hash1[“key3”] = “value3”
```
