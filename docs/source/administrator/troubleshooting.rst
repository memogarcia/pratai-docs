Troubleshooting
===============

API Timeouts
------------

If the API starts to give timeouts to requests, verify:

1. All the services are running.

    >>> http http://{pratai-api}/status

::

    {
        "api": "running",
        "agent": "running"
        "scheduler": "not running",
        "collector": "running",
        "worker {worker_id}": "running",
        "database": "running"
    }

2. Start the compoenents again.