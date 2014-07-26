Supervisor
==========


Installation
--------------------------------------------------
`sudo apt-get install supervisor`


Creating a Program
--------------------------------------------------

#### Create a configuration file
`sudo vim /etc/supervisor/conf.d/djangoapp.conf`

#### Sample program configuration
    [program:djangoapp]
    ; The program to execute
    command=/home/pvergil/Apps/pyenv/py1/bin/gunicorn --workers=2 --bind=0.0.0.0:8000 pev.wsgi:application

    ; Change to this directory before executing the command above
    directory=/home/pvergil/Projects/Python/Django/pev

    ; Start the program when the system boots
    autostart=true

    ; Always restart the program when it exits
    autorestart=true

    ; Define the locations of the log files
    stdout_logfile=/path/to/log.out.log
    stderr_logfile=/path/to/log.err.log


Restarting supervisor
--------------------------------------------------
`sudo service supervisor restart`


Using supervisorctl
--------------------------------------------------

#### Running supervisorctl
`supervisorctl`

#### List processes
`supervisorctl> status`

#### Stopping a process
`supervisorctl> stop PROCESS_NAME`

#### Starting a process
`supervisorctl> start PROCESS_NAME`

#### Exit supervisorctl
`supervisorctl> exit`


#### Shutting down supervisor
`supervisorctl> shutdown`