
## Distributed Systems Exercise

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

### Log-Structured Merge-Tree Algorithm

Consider the following data object:

    "henwen": {
        "age": "103",
        "profession": "Oracular pig"
    }

We could serialize this object to disk using the following format (all numbers are 64-bit unsigned big endian, and all object names, keys and values are ASCII strings):

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

<img src="https://raw.githubusercontent.com/faunadb/exercises/master/distributed-systems/distributed-systems.png" width="50%">

To serialize multiple objects in a single file, we can simply repeat the format for each object. Each file is sorted in ASCII order by object name, and each object's key-value pairs are sorted in ASCII order by key.

If we were building a database, we might accumulate new objects in a buffer pool. Once the buffer pool exceeds a certain size, we would need to flush it to disk in the above format and start over. If an object is updated over time, its keys and values will become spread across many files on disk, and reading it will slow down. To restore read performance, we must merge multiple files into one.

Your task is to implement a compaction function that can merge files in this format.

  - Objects and their inner keys and values must be emitted in the correct order.
  - Any individual object may be too large to fit in memory, so you must process objects incrementally.
  - If the same key appears within the same named object in multiple files, you should choose a strategy to resolve the conflict. Please document the strategy you choose.

Please use a statically typed language for your implementation, if you know one, and include automated tests.

### Input and Output

You can find sample input and output files [here](https://github.com/faunadb/exercises/tree/master/distributed-systems).

### Extra Credit

 * Implement a reader function that lets you retrieve an object by name. Consider the performance implications of your strategy.
