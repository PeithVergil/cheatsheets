Supervisor
==========


Installation
--------------------------------------------------
`sudo apt-get install supervisor`


Configuration (optional)
--------------------------------------------------

#### View default configuration
`echo_supervisord_conf`

#### Save default configuration
`echo_supervisord_conf > /etc/supervisord.conf`


Sample Program
--------------------------------------------------
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

##########################
### Running supervisord
supervisord

# Run supervisord in the foreground
supervisord -n

# The path to a supervisord configuration file
supervisord -c /path/to/supervisord.conf


supervisorctl
--------------------------------------------------

#### Run supervisorctl
`supervisorctl`

#### List processes
`supervisorctl> status`

#### Stopping a process
`supervisorctl> stop PROCESS_NAME`

#### Starting a process
`supervisorctl> start PROCESS_NAME`

#### Exit supervisorctl
`supervisorctl> exit`


##########################
### Shutting down supervisord
supervisorctl> shutdown

####################################
# INIT.D
####################################
# Supervisord auto-start
#
# description: Auto-starts supervisord
# processname: supervisord
# pidfile: /var/run/supervisord.pid

SUPERVISORD=/usr/bin/supervisord
SUPERVISORCTL=/usr/bin/supervisorctl

case $1 in
start)
        echo -n "Starting supervisord: "
        $SUPERVISORD
        echo
        ;;
stop)
        echo -n "Stopping supervisord: "
        $SUPERVISORCTL shutdown
        echo
        ;;
restart)
        echo -n "Stopping supervisord: "
        $SUPERVISORCTL shutdown
        echo
        echo -n "Starting supervisord: "
        $SUPERVISORD
        echo
        ;;
esac
