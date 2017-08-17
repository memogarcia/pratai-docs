Security
========

Enviromental Variables
~~~~~~~~~~~~~~~~~~~~~~

Retreive sensitive data using environmental variables.
::

    # new_module.py
    
    import os

    def main(payload=None):
        user_token = os.environ.get('user_token')

Secrets
~~~~~~~

Secrets are the way to send sensitive data to the functions at runtime. `python-prataiclient` allows you to 
create, list, get and delete secrets.

    >>> pratai secret-create {name}
    >>> please type the value for {name}: 


your function can now implement this secret. **This is work in progress**
::

    # new_module.py

    from prataiclient import Secret

    def main(payload=None):
        secret = Secret(user={your_user}, public_key={pub_key})
        user = secret.get('service_user')


Multitenancy
~~~~~~~~~~~~

By default your functions are available within your tenant, if you want to expose functions to the public,
your tenant should be able to allocate a public IP.

Then, pratai should bind to that IP.

Then you need to expose your function as public
::

    >>> pratai update-function {function_id} --public true

