Deploying the Scheduler
=======================

**This is part of the control plane.**

1. Install the scheduler

    >>> git clone https://github.com/pratai/pratai-scheduler.git
    >>> pip install -e pratai-scheduler/

3. Deploy and configure the API

    >>> sudo mkdir /etc/pratai/
    >>> sudp cp etc/pratai-scheduler.conf /etc/pratai/pratai-scheduler.conf
    >>> sudo vim /etc/pratai/pratai-scheduler.conf

4. Edit the file `/etc/pratai/pratai-scheduler.conf` accordingly:
