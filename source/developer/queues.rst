Distributed Queues
==================

ZeroMQ is the choice for queuing and passing messages in Pratai 
using the PUSH/PULL architecture we can create a pipelines of 
messages that can be distributed across multiple nodes.

.. image:: pushpull.png

Following this apporach we have the following configuration:

API and Agent:

* PUSH on port 5557


Scheduler:

* PULL on port 5557
* PUSH on port 5558


Worker:

* PULL on port 5558
* PUSH on port 5556

Collector:

* PULL on port 5556