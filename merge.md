# Fauna Interview Exercises

Copyright 2014, Fauna, Inc. All rights reserved.

## Merge

Consider the following JSON object:
 
    {
        "creatures/1": {
            "name": "Henwen",
            "description": "Oracular pig"
        }
    }

We can serialized this object to disk using the following format:
 
        Offset | Bytes | Description
    ---------------------------------------------
             0 |     8 | Object Name length (x)
             8 |     x | Object Name
         8 + x |     8 | Key/Value pair count
        16 + x |     8 | Key length (y)
        24 + x |     y | Key
    24 + x + y |     8 | Value length (z)
    32 + x + y |     z | Value
    ....keys and values repeat.... 
 
In the example above, this would be encoded as:
 
    [11|creatures/1|2|4|name|6|Henwen|11|description|12|Oracular pig]
 
To serialize multiple JSON objects, we simply repeat the format for
each object until EOF. Each file is sorted alphabetically by object
name, and each object's key/value pairs are sorted by key.
 
Once we've encountered 1MB worth of these key/value pairs, we write
out a new file. In this way, an object's key/value pairs might be
spread across many files on disk.
 
For instance, if the file containing the object above has reached its
file size limit and we'd like to add the pair `"age": "120"` to
`creatures/1`, we would add a section to a new file with:
 
    [11|creatures/1|1|3|age|3|120]
 
Assuming the data set is too large to fit in memory, implement an iterator (such as `java.util.Iterator`) which will combine a set of data files and yield each object and its entire set of key/value pairs. The iterator must maintain the correct sort order as specified above. Assume that there will be no conflicts.

Please use Scala or another statically typed language for your implementation.

