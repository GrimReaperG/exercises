
## Full Stack Exercise

Copyright 2015, Fauna, Inc. All rights reserved. For general instructions, see [here](https://github.com/faunadb/exercises/blob/master/README.md).

### Mailinator

Mailinator is a web service for checking email sent to public, temporary email addresses. There are many similar services, but Mailinator was one of the first.

Your task is to implement an API service that performs the same functions as Mailinator. It should expose the following HTTP endpoints.

 - `POST /mailbox`: Create a random email address.
 - `POST /mailbox/{email address}`: Send a message to a specific email address at the service.
 - `GET /mailbox/{email address}`: Retrieve an index of messages received at a particular email address, including sender, subject, and id, in recency order. Support cursor-based pagination through the index.
 - `GET /message/{message id}`: Retrieve a specific message by id.

Whether email addresses need to be explicitly created in order to receive messages is up to you.

Additional requirements:

  - The input and output formats should be well-structured JSON.
  - Old messages must eventually be expired, so you'll need to implement an eviction or garbage collection strategy.
  - Make sure to support concurrent access, either through multi-threading or multi-processing.

Please use a statically typed language for your implementation, if you know one, and the application framework of your choice. You may use a database, but you don't have to. Document your code and include automated tests.

### Extra Credit

The original Mailinator service ran as a single Java process on a single machine, storing all data on the heap.

 - Implement a solution that stores all data entirely in-memory and in-process (do not use Redis or a similar memory store, and do not write to disk). Make sure to manage the size of the process heap to avoid OOM exceptions.
 - Include an automated benchmark suite that measures the performance of your solution. Suggest some ways to improve performance.
 - Support receiving messages via SMTP.