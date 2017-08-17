Building the docs
=================

The docs are the main source of documentation for pratai.

    >>> git clone https://github.com/pratai/pratai-docs.git
    >>> pip install -r pratai-docs/requirements.txt
    >>> cd pratai-docs/docs/
    >>> sphinx-build -b html source build

Then, open `build/index.html` in your browser.