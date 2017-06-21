Deploying the API
=================

**This is part of the control plane.**

1. Install pratai-api

    >>> git clone https://github.com/pratai/pratai-api.git
    >>> pip install -e pratai-api/

2. Deploy and configure the API

    >>> sudo mkdir /etc/pratai/
    >>> sudp cp etc/pratai-api.conf /etc/pratai/pratai-api.conf
    >>> sudo vim /etc/pratai/pratai-api.conf

3. Edit the file `/etc/pratai/pratai-api.conf` accordingly:


4. Initialize the database

    >>> pratai-db-init start

5. Set AWS credentials for S3

    >>> export AWS_SECRET_KEY=''
    >>> export AWS_ACCESS_KEY=''

6. Run the API

    >>> pratai-api start
