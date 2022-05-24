# Read: 30 - Hash Tables 

# Content  

# Intro to Hash Tables  
Hash A hash is the output of an algorithm that converts an input string into a value that may be used for security or any other purpose. It is used to find the index
of the array in the case of a hashtable. Buckets What is contained in each index of the hashtable's array is referred to as a bucket. Each index corresponds to a bucket.
If a collision happens, an index might include several key/value pairs. Collisions occur when several keys are hashed to the same place in the hashtable. Hashtables may
be used to store unique data, dictionaries, and libraries. Hashtables are key-value pairs-based data structures. This implies that each Node and Bucket has both a key
and a value associated with it. The ability to put the key in this data structure and get the value fast using a hash, A hash is the ability to encode a key that will
eventually map to a specific position in the data structure that we can look at to obtain the item directly. In an ideal world, Big O(1) is used, while in a worst-case
scenario, O is used (n). A hash code converts a key into an integer, and the output is solely defined by the input. Traditionally, a hashtable is built from an array.
The array's indexes can hold a variety of values. The array's indexes include "buckets," each of which contains one key/value pair combination. When more than one key
hashes to the same index in an array, collision occurs. Any number of buckets can be used in a hash map. A hash map with only a few buckets will be highly packed and
have a lot of collisions. A hash map with more buckets will be poorly populated, resulting in fewer collisions but potentially a lot of vacant space. The load factor
informs us about how filled the hash table is. When adding a new key/value combination to a hashtable, use Add(). Find() accepts a key, calculates the Hash, and navigates
to the provided index position. Contains() accepts a key and returns a bool indicating whether that key exists in the hashtable. GetHash() accepts a string as a key,
performs the hash, and returns the index of the array where the key/value should be stored.  

# What is a HashTable Data Structure - Introduction to Hash Tables , Part 0  
Information is stored in hash tables. A key and a value are the two essential components. A method for creating an associative array. A key value is sent to the hash
function, which returns an index number. The key will always match that index number, but if another key with the same index appears, you'll need to create a chain
from the unit it's in. Hash tables may be rather big and hold a lot of data.  

# Basics of Hash Tables  
Hashing is a technique for distinguishing a single object from a bunch of similar ones. Hash functions are used to transform large keys into tiny ones. Any function that
may be used to translate a data set of any size to a data set of a defined size that falls into the hash table is referred to as a hash function. Hash values, hash codes,
hash sums, or simply hashes are the values returned by a hash function. The values are then stored in a hash table, which is a type of data structure. A hash table is a
data structure for storing key-value pairs. Defining the fundamental needs Simple to calculate It must be simple to compute and not become an algorithm in and of itself.
Distribution that is consistent It should provide a consistent distribution over the hash table and avoid clustering. There are fewer collisions. When two items are
mapped to the same hash value, a collision occurs. These should be avoided at all costs. Separate chaining, which is performed using linked lists, is one of the most
widely used collision resolution strategies. All entry records are kept in the array itself, using open addressing. When a new entry is required, the hash index of
the hashed value is calculated, and the array is then inspected. The probe sequence is the path taken when traveling through entries. The interval between successive
probes is set in linear probing. The sole difference between quadratic and linear probing is the gap between subsequent probes or entry slots. Associative arrays are
arrays with arbitrary strings or other complex items as indices. Hash tables for database indexing can also be utilized as disk-based data structures or database
indices. Caches can be implemented using hash tables. Hash tables are used to implement objects in numerous dynamic languages, including Perl, Python, JavaScript,
and Ruby. Hash functions are employed in a variety of techniques to speed up computation.
