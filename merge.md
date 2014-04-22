# Fauna Interview Exercises

Copyright 2014, Fauna, Inc. All rights reserved.

## Merge

Consider the following JSON object:
 
```
{
    "foo": {
        "bar": "baz",
        "quux": "xyzzy"
    }
}
```
 
We can serialized this object to disk using the following format:
 
    Offset | Bytes | Description
--------------------------------------
         0 |     8 | Object Name length (x)
         8 |     x | Object Name
     8 + x |     8 | Key/Value pair count
    16 + x |     8 | Key length (y)
    24 + x |     y | Key
24 + x + y |     8 | Value length (z)
32 + x + y |     z | Value
 
In the example above, this would be encoded as:
 
    [3|foo|2|3|bar|3|baz|4|quux|5|xyzzy]
 
To serialize multiple JSON objects, we simply repeat the format for
each object until EOF. Each file is sorted alphabetically by object
name, and each object's key/value pairs are sorted by key.
 
Once we've encountered 1MB worth of these key/value pairs, we write
out a new file. In this way, an object's key/value pairs might be
spread across many files on disk.
 
For instance, if the file containing the object above has reached its
file size limit and we'd like to add the pair `"kludge": "cruft"` to
`foo`, we would add a section to a new file with:
 
    [3|foo|1|6|kludge|5|cruft]
 
Assuming the data set is too large to fit in memory, write an iterator
which will combine a set of data files and yield each object and its
entire set of key/value pairs. Assume that there will be no conflicts.

Please write the iterator in a statically-typed language.

