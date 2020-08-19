Environment
===========

Install the required packages

    sudo apt-get install python-pip python-virtualenv gettext optipng libjpeg-turbo-progs

Using a python (2.7) virtualenv is recommended.

Create a virtualenv

    virtualenv --python=/path/to/python2.7 pelican_env

Use virtualenv

    source pelican_env/bin/activate

Install Python modules
    
    // upgrade pip
    pip install pip --upgrade
    pip install setuptools --upgrade

    pip install -r requirements.txt

Enable Pelican plugins

    git submodule init
    git submodule update

Building
========

    make html


Build for upload in Freenet
---------------------------

    source pelican_env/bin/activate
    PYTHONPATH=$PYTHONPATH:pelican-plugins{$(ls pelican-plugins/| sed 's/ /,/g')} make html SITEURL=/USK@0iU87PXyodL2nm6kCpmYntsteViIbMwlJE~wlqIVvZ0,nenxGvjXDElX5RIZxMvwSnOtRzUKJYjoXEDgkhY6Ljw,AQACAAE/freenetproject-mirror/490/ DEBUG=1 && freesitemgr update freenetproject-mirror

Testing 
=======

    firefox output/index.html
