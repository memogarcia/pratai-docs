Deploy Pratai
=============

Manual Installation
~~~~~~~~~~~~~~~~~~~

Install pip and virtualenv first.

    >>> sudo apt-get install python-pip
    >>> pip install pip --upgrade
    >>> pip install virtualenv --upgrade

Also, Pratai development is focus on python 3.5 and its async capabilities so,
use python 3 in your virtualenv. We recomment using a virtualenv per project.

    >>> virtualenv -p python3.5 {pratai-repo}/.venv
    >>> source {pratai-repo}/.venv/bin/activate


.. toctree::
   :maxdepth: 2

   initialize_db
   install_docs
   install_api
   install_agent
   install_scheduler
   install_drivers
   install_runtimes
   install_client


Development deployment
~~~~~~~~~~~~~~~~~~~~~~

Run this ansible script to deploy pratai in docker


OpenStack deployment
~~~~~~~~~~~~~~~~~~~~

For Openstack follow the steps in:

.. toctree::
   :maxdepth: 2

   control_plane
   pratai_nodes