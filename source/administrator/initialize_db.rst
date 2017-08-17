Configuring the db
==================

1. Install elasticsearch

    >>> sudo apt-get install openjdk-7-jre -y
    >>> wget https://download.elastic.co/elasticsearch/elasticsearch/elasticsearch-1.7.5.deb
    >>> sudo dpkg -i elasticsearch-1.7.5.deb
    >>> sudo service elasticsearch start

2. Create the index

    >>> 