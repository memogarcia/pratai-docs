Data Structures
===============

This are the data structures that are used in pratai.

WebHook request
---------------

This is the json request comming from an HTTP POST
::

    {
        "payload": "payload"
    }


Message request
---------------

This is the json request for the scheduler
::

    {
        'action': action,
        'payload': payload,
        'request_id': request_id,
        'function_id': function_id
    }

Logs structure
--------------

Build function structure
------------------------

This is the structure need it to build functions.
::

    {
        "user_id": "user_id",
        "tenant_id": "tenant_id",
        "name": "name",
        "description": "description",
        "event": "event",
        "runtime": "runtime",
        "type": "type",
        "memory": "memory",
        "zip_location": "zip_location",
        "tags": "tags"
    }

Job Structure
-------------

This is the job that is send to the functions
::

    {
        "user_id": "user_id",
        "tenant_id": "tenant_id",
        "function_id": "function_id",
        "image_id": "image_id",
        "request_id": "request_id",
        "action": "execute",
        "payload": "payload"
    }


Result Structure
-----------------

This is the result from the executed function.
::

    {
        "user_id": "user_id",
        "tenant_id": "tenant_id",
        "function_id": "function_id",
        "request_id": "request_id",
        "payload": "payload",
        "run_id": "run_id",
        "status": "status",
        "time_took": "time_took",
        "started_at": "started_at",
        "finished_at": "finished_at"
    }


Cluster Structure
-----------------

This is the information about the cluster.
::

    {
        "daemon_type": "daemon_type",
        "daemon_id": "daemon_id",
        "joined_at": "datetime.now()",
        "status": "running",
        "ip": "ip"
    }