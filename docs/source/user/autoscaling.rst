Autoscaling
===========

By default pratai scales horizontally very quickly and easy, by spawning a function per request, 
but you can limit the number of functions that can be created at any given time.

    >>> pratai function-update {function_id} --limit 50