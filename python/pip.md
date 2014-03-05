Pip
===


Installation
--------------------------------------------------
`sudo apt-get install build-essential python-dev python-pip`


Listing installed packages
--------------------------------------------------
`pip freeze`


Installing specific versions
--------------------------------------------------
`pip install 'Django==1.4.2'`


Upgrading
--------------------------------------------------
`pip install -U Django`


Uninstalling
--------------------------------------------------
`pip uninstall PIL`


Installing a package from a tarball
--------------------------------------------------
`pip install path/to/mypackage.tgz`


Installing a package from a tarball over HTTP
--------------------------------------------------
`pip install http://dist.repoze.org/PIL-1.1.6.tar.gz`


Installing a package from a repository
--------------------------------------------------
`pip install git+https://github.com/mariocesar/sorl-thumbnail`


Installing from a requirements file
--------------------------------------------------
`pip install -r requirements.txt`


Display package info and dependencies
--------------------------------------------------
`pip show django-celery`