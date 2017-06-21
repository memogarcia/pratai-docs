Using Pratai
============

Installing prataiclient
~~~~~~~~~~~~~~~~~~~~~~~
::

    >>> git clone https://github.com/memogarcia/python-prataiclient
    >>> pip install -e python-prataiclient


Set up the client
~~~~~~~~~~~~~~~~~
Pratai requires OpenStack credentials to work.
::

    export OS_PRATAI_URL=http://localhost:9998
    export OS_USERNAME=user
    export OS_PASSWORD=pass
    export OS_AUTH_URL=http://localhost:5000/v3
    export OS_TENANT_NAME=pratai
    export OS_IDENTITY_API_VERSION=3
    export OS_PROJECT_DOMAIN_NAME=Default
    export OS_USER_DOMAIN_NAME=Default

On Windows use `set` instead of `export`


Creating an async function
~~~~~~~~~~~~~~~~~~~~~~~~~~
Start by listing all the available options in pratai::

    >>> pratai help


List all the runtimes available to use::

    >>> pratai runtime-list
    

Now that we can choose a `python27` runtime to deploy our function, we can start the actual coding. 
In this case it will be a demo function, it doesn't do anything but return the input as output. Please 
follow the next steps:

1. Create a `new_module.py` file
::

    import numpy
    # yes you can install dependencies, just send a requirements.txt

    def local_function(payload):
        # you can create local functions
        return payload

    def main(payload=None):
        # a main function should always be declared
        # and using a payload as a parameter
        return local_function(payload)


2. create a `requirements.txt` file with the dependencies
::

    numpy


This file should be present, doesn't matter if is empty.


3. Create a zip file containing only the `new_module.py` and  `requirements.txt` files, everything else 
will be ignored. And make sure that those 2 files are at the root of the zip file
::

    package.zip
      - new_module.py
      - requirements.txt


4. Deploy our function

    >>> pratai function-create {name} --zip /path/to/zip


This will return the id of the new function.

**Optional** Creating a function accepts more parameters.

    >>> pratai help function-create


Listing functions

    >>> pratai function-list

Listing only the ID's (helpful when dealing with lots of functions).

    >>> pratai function-list --only-id -f value


Getting a function

    >>> pratai function-show {function_id}

Output (not the actual one)::

    +-------------+-----------------------------------------------------------------+
    | Field       | Value                                                           |
    +-------------+-----------------------------------------------------------------+
    | function_id | b2e9b5933f57417c8540a2d7e8b88289                                |
    | user_id     | 63123ed9644447df8315a74052314865                                |
    | tenant_id   | b2cef86662f34faeb0df0fc3b657c8ef                                |
    | name        | name_of_function                                                |
    | description |                                                                 |
    | type        | async                                                           |
    | event       | webhook                                                         |
    | public      | False                                                           |
    | endpoint    | http://localhost:9898/function/b2e9b5933f57417c8540a2d7e8b88289 |
    | runtime     | python27                                                        |
    | memory      | 128                                                             |
    | cpus        | 1                                                               |
    +-------------+-----------------------------------------------------------------+

Naming Conventions
~~~~~~~~~~~~~~~~~~
A function should always implement a main function that accept a payload
::

    def main(payload=None):
        local_function(payload)


Logging
~~~~~~~
Pratai uses the python standard library logging module, in order to use the centralized logger use the following:
::

    import logging
    logger = logging.getLogger('pratai')

    logger.debug()
    logger.info()
    logger.error()
    logger.critical()


Zipping your functions
~~~~~~~~~~~~~~~~~~~~~~

Pratai accepts a function that is archived in a zip file. Each zip file has to have:

* `requirements.txt`, even if is empty.
* `new_module.py`, with your custom code.
* every other file in the zip will be ignored.


Executing a function
~~~~~~~~~~~~~~~~~~~~

Now your function can be executed by sending an HTTP POST request to the endpoint assigned to this function::

    >>> curl \
        -H "Content-Type: application/json" \
        -X POST -d \
        '{"payload":{"key": "value"}}' \
        http://localhost:9898/function/b2e9b5933f57417c8540a2d7e8b88289

**Make sure your request contains a payload key in your json**

The ouput of this execution is not the response of the function but a `request_id`.

Due to the asynchronous nature of the platform the your function will be executed in the background, but you can track it like this.::

    >>> pratai request-list --filter {request_id}

This will list all the request made to the function, so you can track logs, responses, status, etc.

Later a `wait_for_response` option will be added to the functions, this will allow you to create code that returns an actual response immediately.