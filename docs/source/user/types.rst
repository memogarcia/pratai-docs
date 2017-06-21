Events
======

Async
~~~~~

This is the default event for pratai, it will take a request or a message and procees it asynchronously, then, 
you can collect the logs or responses, by default the response gets stored in a collector queue, 
that can send this response as an input for other functions.

Type
----

You can use the async event in the following cases:

1. **Async + Webhook**

This is the default behaviour, in which a function will be executed asynchronously when an HTTP POST requests
hists its endpoint.

    >>> pratai function-create {name} --type async --event webhook


2. **Async + Message**

A function created with this configuration will executed asynchronously when a message arrives in the event 
queues available for the platform.

    >>> pratai function-create {name} --type async --event message --subscribe_to {event_id}


3. **Async + Timer**

A function created with this configuration will executed asynchronously everytime a timer sends an event,
the frequency of the events are set in minutes.

    >>> pratai function-create {name} -type async --event timer --frequency 5


Wait for Reponse
~~~~~~~~~~~~~~~~

This is a request that works like a tipical web server, you send a request and you wait for a reponse and only works 
for webhooks events
::

    >>> pratai function-create {name} --type wait_for_response --event webhook