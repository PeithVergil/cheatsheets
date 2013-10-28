Gunicorn
========

Installing Gunicorn
--------------------------------------------------
`pip install gunicorn`


Running Django with Gunicorn
--------------------------------------------------
`gunicorn -c /path/to/config.py myproject.wsgi:application`


Gunicorn configuration file
--------------------------------------------------
    bind = '127.0.0.1:8000'
    workers = 3
    errorlog = '/path/to/errorlog'
    accesslog = '/path/to/accesslog'
    worker_class = 'gevent'


Installing Gevent
--------------------------------------------------

#### Installing dependencies

If using Gevent < 1.0

`sudo apt-get install libevent-dev`

If using Gevent >= 1.0

`sudo apt-get install libev-dev`


#### Installing the package
`pip install gevent`