Payload
=======

Payload is the data that the function needs in order to run, a function accepts `string`, `int`, `lists`, `json` and an `empty` value.
but **not** files at the moment.

The max size of the payload by default is `6MB`.

all payloads should always be wrapped as json and have `payload` as a key and the actual payload as a value. E.g.

`string` payload::

    {
        "payload": "string"
    }

`int` payload::

    {
        "payload": 3
    }

`list` payload::

    {
        "payload": ['string1', 2, {}]
    }

`json` payload::

    {
        "payload": {
            "key": "value"
        }
    }

`empty` payload::

    {
        "payload": {}}
    }