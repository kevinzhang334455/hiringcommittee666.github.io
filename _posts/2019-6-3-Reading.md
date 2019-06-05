---
layout: post
title: Hello World!!!
---

First Hello world blog.

Today's Reading summary:
1. Weak Isolation consistency

Iso level:
    a) Read commit isolation. It needs to guaranttee two things:
        i. When reading from the database, you will only see data that has been committed (no dirty reads).
        ii. WHen writing to the database, you will only overwrite data that has been committed (no dirty writes).

    b) Snapshot Isolation -- the transaction sees all the data that was committed in the database at the start of the transaction. Even if the data is subsequently changed by another transaction,
       each transaction sees only the old data from that particular point in time. 

       MY Understanding is that b) is more strict isolation policy than a) because a) can see intermediate results from other transactions among
       reading / writing operations from this transaction.

2. Eventual consitency
    a) Hinted Headoff queue.
       Hinted Headoff queue is basically a local disk queue which stores the data that is not successfully replicated.   

    b) Anti-entropy.
       Basically to gossip (propagate) latest version of data. (Fit for leader-less replication.)

       Use Merkle tree for the implementation.
       https://stackoverflow.com/questions/5486304/explain-merkle-trees-for-use-in-eventual-consistency
