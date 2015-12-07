# Defining/creating hash

## Java

In java the class HashMap provides the implementation of the hash. The HashMap has following constructors to create the object.

```HashMap()```
Constructs an empty HashMap with the default initial capacity (16) and the default load factor (0.75).

```HashMap(int initialCapacity)```
Constructs an empty HashMap with the specified initial capacity and the default load factor (0.75).

```HashMap(int initialCapacity, float loadFactor)```
Constructs an empty HashMap with the specified initial capacity and load factor.

```HashMap(Map<? extends K,? extends V> m)```
Constructs a new HashMap with the same mappings as the specified Map.

If the null is not to be a valid key then instead of HashMap, use HashTable class. Both of them have same methods
An example of usage of these APIs is

```java
HashMap hashMap = new HashMap();
```

## Perl

In perl hashes are defined as below

```perl
my %hash1 = ();
```

If hash reference is to be defined and intialized to empty set, it is done as follows

```perl
my $hash1Ref = {};
```

Above hashes can be initialized with some keys and values as below

```perl
%hash1 = (‘key1’ => ‘value1’,
    ‘key2’ => ‘value2’,
    ‘key3’ => ‘value3’
    );
```

Similarly hash reference can be initialized as below

```perl
$hash1Ref = {‘key1’ => ‘value1’,
       ‘key2’ => ‘value2’,
       ‘key3’ => ‘value3’
      };	
```

## C
In C there is no data structure built in for hashes. These has to be written by the developers. There are really 2 options here viz write your own hash implementation or use an implementation that has been developed by some organization and is being used by software developers. For C some of the well known hash implementation libraries are sglib , cbfalconer, glib (gnome hash),Judy, npsml, strmap, uthash, libcfu. Each of the libraries have their some advantages or disadvantages. Evaluating this is beyond the scope of this book. For the purpose of this book, I chose libcfu library because it is well written library and easy to integrate from developer point of view.  This may or may not be true for all cases. To use libcfu, follow the installation instructions. After successful installation include cfuhash.h header file in the C file in which the libcfu functions are being used.
A new hash is create as below using function cfuhash_new_with_initial_size which takes in the initial size of the hash

```c
cfuhash_table_t *hash = cfuhash_new_with_initial_size(10);
```

There are 4 functions that can be used to create a new hash table

```c
/* Creates a new hash table. */
cfuhash_table_t * cfuhash_new();

/* Creates a new hash table with the specified size (number of buckets). */
cfuhash_table_t * cfuhash_new_with_initial_size(size_t size);

/* Creates a new hash table with the specified flags.  Pass zero for flags if you want the defaults. */
extrn cfuhash_table_t * cfuhash_new_with_flags(u_int32_t flags);
   
/* Same as cfuhash_new() except automatically calls cfuhash_set_free_fn(). */
cfuhash_table_t * cfuhash_new_with_free_fn(cfuhash_free_fn_t ff);
```

## Bash
The hashes in Bash are known as associative arrays. There are supported after bash version 4.
The hashes in Bash is defined using declare statement as below

```bash
declare -A hash1
```
