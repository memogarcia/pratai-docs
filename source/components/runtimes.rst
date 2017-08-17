Runtimes
========

* License: Apache License, Version 2.0
* `PyPi`_ - package installation
* `Launchpad project`_ - release management
* `Blueprints`_ - feature specifications
* `Bugs`_ - issue tracking
* `Source`_
* `Specs`_


OS Layer
--------


Python 2.7
----------


Build your own runtime
----------------------

If you need add or modify existing runtimes you should follow this very simple guidelines:

* Don't execute anything under root.
* That's it.

You can take a look to the seed Dockerfile in the pratai-runtimes repo for more examples.

Once you have that ready you can create your own runtime by creating just another Dockerfile 
with the tools and dependencies you need.

Then, you need to build the new runtime in each node.

    >>> mkdir /etc/pratai/runtimes/custom_runtime
    >>> cp Dockerfile /etc/pratai/runtimes/custom_runtime/
    >>> docker build -t pratai/custom_runtime /etc/pratai/runtimes/custom_runtime/

And there you go.



.. _PyPi: https://pypi.python.org/pypi/pratai-runtimes
.. _Launchpad project: https://launchpad.net/pratai-runtimes
.. _Blueprints: https://blueprints.launchpad.net/pratai-runtimes
.. _Bugs: https://bugs.launchpad.net/pratai-runtimes
.. _Source: https://github.com/pratai/pratai-runtimes
.. _Specs: http://specs.openstack.org/openstack/pratai-specs/