========
Concepts
========

Namespace
----------
A coherent set of services working together to run OpenIO's solutions.


Account
--------
Usually represents a customer (the second 'B' in B2B2C). There is
no limit to the number of accounts in a namespace. Accounts keep track of
namespace usage of each customer (e.g. the list of containers and
the number of bytes occupied by all objects of a customer).


Reference
----------
Some kind of service container. Usually represents a final user
(the 'C' in B2B2C). Several services may be linked to a reference
(e.g. an object storage service and a database service).
More details in `Service Directory`_ section.


Containers
----------
Object buckets. They keep track of object locations.
A container belongs to one (and only one) account.
More details in `Object Storage`_ section.


Objects
-------
The smallest data units visible by customers. An object belongs
to one (and only one) container.


Chunks
------
Parts of objects, not visible by customers. They are limited in size.
They can be replicated or be accompanied by parity chunks.


Conscience
----------
A (set of) service(s) responsible for collecting,
aggregating and distributing metrics about all other services of a namespace,
in order to have a good load balancing and data placement.
More details in Conscience_ section.


Services
--------
Processes running in the namespace. They can be stateless or stateful,
are load-balanced by the conscience, and can be linked to several references.


Scores
------
An aggregation of metrics reflecting the health of each service, usually
between 0 and 100. Scores are computed by Conscience, and used by
load-balancers. See `Load Balancing`_.


.. _`Service Directory`: ./directory.html
.. _`Object Storage`:    ./objectstorage.html
.. _Conscience:          ./conscience.html
.. _`Load Balancing`:    ./conscience.html#load-balancing

