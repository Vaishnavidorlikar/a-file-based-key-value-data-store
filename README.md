Problem statement

Build a file-based key-value data store that supports the basic CRD (create, read, and dclete)

operations.This data store is meant to be used as a local storage for one single process on one

laptop.The data store must be exposed as a library to clients that can instantiate a class and work

with the data store.

The data store will support the following functional requirements.

1. It can be initialized using an optional file path.If one is not provided, it will reliably

create itself in a reasonable location on the laptop.

2. A new key-value pair can be added to the data store using the Create operation.The key

is always a string -capped at 32chars.The value is always a ISON obiect - capped at

16KB.

3,If Create is invoked for an existing kev.an appropriatecrror must be returncd.

4. A Read operation on a key can be performed by providing the key, and receiving the

value in rcsponsc,as aJSON objcct.

5. A Delete operation can be performed by providing the key.

6.Every key supports sctting a Time-To-Live property when it is created.This propcrty is

ontional. If erovided it will be evaluated as an inteeer definine the number of seconds

the key must be rctained in the data store.Once the Timc-To-Live for a key has expired,

the key will no longer be available for Read or Delete operations.

7.Appropriate error responses must always be returned to a clicnt if it uses the data store in

uncxpectedways or breaches anylimits_

The data store will also support the following non-functional requirements.

1. The size of the fle storing data must never exceed 1GB.

2.More than one client process cannot be allowed to use the same file as a data store at any

given time.

3,A clicnt proccss is allowed to access the data storc using multiplce threads, if it desircs to.

The data store must thcrefore be thread-safe.

4. Thc client will bear as littlc memory costs as possiblc to usc this data store, whilc

dcriving maximum pcrformance with respect to response timcs for acccssing the data

store.




