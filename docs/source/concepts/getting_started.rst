Getting Started with Pratai
===========================


With traditional long-running virtual machines or containers, it is common practice to deploy 
multiple VMs or containers to be resilient against outages of a single instance. 

However, Pratai offers an alternative model with no resiliency-related cost overhead. 
The on-demand execution of actions provides inherent scalability and optimal utilization as 
the number of running actions always matches the trigger rate. Additionally, the developer now only 
focuses on his code and does not worry about monitoring, patching, and securing the underlying server, 
storage, network, and operating system infrastructure.


What is Pratai?
~~~~~~~~~~~~~~~

Pratai offers an event driven platform to provide serverless applications and services to OpenStack.

Pratai provides an incredible flexibility on how to migrate workloads to the cloud that respond to events without 
having to manage any server or network, this allows your systems to be more flexible, loosely-coupled, scalable and 
easier to develop while offering a more tolerant to failure environments.


How it works?
~~~~~~~~~~~~~

Pratai's goal is simple. Deploy code (disclaimer, from now on this document will refer to code as functions), that will
react to an event without worrying about anything else, the platform handles the execution. Simple right?

In order to achieve that, first, we need to deploy a function in a `zip` format for one of the languages that the 
platform supports, the first one is python but more will be added in the future, after this a docker image 
gets created with the custom function and its dependencies. e.g.::

    # new_module.py

    import numpy
    # yes you can install dependencies, just send a requirements.txt

    def local_function(payload):
        # you can create local functions
        return payload

    def main(payload=None):
        # a main function should always be declared
        # and using a payload as a parameter
        return local_function(payload)

When a function gets created it will remain as inactive, waiting to be executed whenever an event happens that 
the function is subscribed to, could be a http request, a message from a monitoring platform, an event in a service in
the infrastructure or the cloud but basically every event will execute the function an then it will dissapear.
