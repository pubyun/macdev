# Configuration of the dev environment of Python

## Python (optional)
Although Mac OS X comes with Python, we can use Homebrew to intall Python 2.7.x because

* Use Homebrew to install more recent version of Python
* Intall Python 2.7.x and 3.x at the same time
* Homebrew will install tools like setuptools and pip

To install Python 2.7.x

    brew install python --with-brewed-openssl

To install Python 3.x

    brew install python3 --with-brewed-openssl

## pip

We use pip to manage packages:

    sudo easy_install pip

## virtualenv virtualenvwrapper

To install packages: 

    sudo pip install virtualenv virtualenvwrapper

To create the virtualenv folder

    mkdir ~/virtualenvs

To config virtualenv in .zshrc or .bash_profile

    # virtualenvwrapper
    export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python
    export WORKON_HOME=~/virtualenvs
    [ -f /usr/local/bin/virtualenvwrapper.sh ] && source /usr/local/bin/virtualenvwrapper.sh
    [ -f /etc/bash_completion.d/virtualenvwrapper ] && source /etc/bash_completion.d/virtualenvwrapper
    export PIP_VIRTUALENV_BASE=$WORKON_HOME
    export PIP_RESPECT_VIRTUALENV=true


To create the first python 2 virtualenv:

    mkvirtualenv test

To create the first python 3 virtualenv:

    mkvirtualenv -p python3 test

## PyCharm

PyCharm is the best Python IDE so far. There are community and professional versions for you to choose.

