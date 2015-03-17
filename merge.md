# Fauna Interview Exercises

Copyright 2015, Fauna, Inc. All rights reserved.

## Merge Algorithm

Consider the following data object:

    "henwen": {
        "age": "103",
        "profession": "Oracular pig"
    }

We could serialize this object to disk using the following format (all numbers are 64-bit, unsigned, big endian):

        Offset | Bytes | Description
    ---------------------------------------------
             0 |     8 | Object name length (x)
             8 |     x | Object name
         8 + x |     8 | Number of key-value pairs
        16 + x |     8 | Key length (y)
        24 + x |     y | Key
    24 + x + y |     8 | Value length (z)
    32 + x + y |     z | Value
    ....keys and values repeat....

In the example above, this would be encoded as:

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/merge.png" width="66%">

To serialize multiple objects in a single file, we can simply repeat the format for each object. Each file is sorted alphabetically by object name, and each object's key-value pairs are sorted alphabetically by key.

If we were building a database, we might accumulate new objects in a buffer pool. Once the buffer pool exceeds a certain size, we would need to flush it to disk in the above format and start over. If an object is updated over time, its keys and values will become spread across many files on disk, and reading it will slow down. To restore read performance, we must merge multiple files into one.

Your task is to implement a compaction function that can merge files in this format.

  - Objects and their inner keys and values must be emitted in the correct order
  - The input and output files may be too large to fit in memory, so you must process them incrementally
  - If the same key is present within an object in multiple files, you can resolve the conflict any way that you choose

Please use a statically typed language for your implementation, if you know one, and include automated tests.

### Input and output

You can find sample input and output files here: https://github.com/fauna/exercises/tree/master/merge

### Extra credit

Implement a reader function for a set of files in the above format that lets you retrieve any particular merged object by name. Again, avoid loading the entire file contents into memory. Consider the performance implications of your reader strategy.
