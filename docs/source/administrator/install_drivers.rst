Deploying the Drivers
=====================

**This is part of the pratai nodes.**

1. Install the drivers.

    >>> git clone https://github.com/pratai/pratai-drivers.git


2. Configure the API.

    >>> sudo mkdir /etc/pratai/pratai-driver.conf
    >>> sudo cp etc/pratai-driver.conf /etc/pratai/pratai-driver.conf
    >>> sudo vim /etc/pratai/pratai-driver.conf


Enable Docker Driver
--------------------

Enable docker to be accesible by `tcp`:

1. Edit `/etc/default/docker`:
::

    DOCKER_OPTS='-H tcp://127.0.0.1:4243 -H unix:///var/run/docker.sock'

2. Restart docker

    >>> sudo service docker restart


3. Edit the file `/etc/pratai/pratai-driver.conf`:
::

    [queue]
    endpoint = tcp://127.0.0.1:5558

    [api]
    url = 127.0.0.1
    port = 9997


4. Deploy the runtimes

.. toctree::
   :maxdepth: 2

   install_runtimes
    

5. Running the driver worker

    >>> pratai-driver-worker start


5. Running the driver API

    >>> pratai-driver-api start


Deploy API and Worker inside a container
----------------------------------------

**Optional**

We can leverage docker orchestration by deploying the api and the worker in a container.

    >>> docker run -it -v /var/run/docker.sock:/var/run/docker.sock pratai/driver-docker-api:latest
    >>> docker run -it -v /var/run/docker.sock:/var/run/docker.sock pratai/driver-docker-worker:latest