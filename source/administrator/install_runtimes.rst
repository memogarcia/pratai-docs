Deploying the Runtimes
======================

**This is part of the pratai nodes.**

1. Create `/etc/pratai` directory.

    >>> sudo mkdir /etc/pratai/

2. Clone the repo in `/etc/pratai`, *you may need sudo*

    >>> git clone https://github.com/pratai/pratai-runtimes.git /etc/pratai/


3. Build the base docker image.

    >>> docker build -t pratai/seed /etc/pratai/runtimes/seed/


4. Build python27 runtime.

    >>> docker build -t pratai/python27 /etc/pratai/runtimes/python27/
