Scheduler
=========

* License: Apache License, Version 2.0
* `PyPi`_ - package installation
* `Launchpad project`_ - release management
* `Blueprints`_ - feature specifications
* `Bugs`_ - issue tracking
* `Source`_
* `Specs`_


The scheduler primarily consists of a set of Python daemons, 
though it requires and integrates with a number of native system 
components for databases and messaging capabilities.

Scheduler
---------

The API and the Agent push messages to this queue which will be pre-processed before being 
distributed among the pratai nodes.


Collector
---------

When a function finish the function execution it will send the result and status here in order to be stored 
in the database afterwards.


.. _PyPi: https://pypi.python.org/pypi/pratai-scheduler
.. _Launchpad project: https://launchpad.net/pratai-scheduler
.. _Blueprints: https://blueprints.launchpad.net/pratai-scheduleragent
.. _Bugs: https://bugs.launchpad.net/pratai-scheduler
.. _Source: https://github.com/pratai/pratai-scheduler
.. _Specs: http://specs.openstack.org/openstack/pratai-specs/