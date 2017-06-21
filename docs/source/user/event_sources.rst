Event Sources
=============

Webhook
~~~~~~~

When a function gets created with an `--event webhook`, it will get assigned an HTTP POST endpoint in which you can 
reach that function

Messages
~~~~~~~~

Functions created with this event: `--event message` won't have an HTTP endpoint assigned, rather, you need to susbscribe to 
an event
::

    >>> pratai event-list
