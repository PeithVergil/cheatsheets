Supervisor
==========


Installation
--------------------------------------------------

Install `supervisor` globaly using Ubuntu's package manager.

```bash
sudo apt-get install supervisor
```


Creating a program
--------------------------------------------------

Create a configuration file.

```bash
sudo vim /etc/supervisor/conf.d/myapp.conf
```

A sample program configuration:

```ini
[program:myapp]
; The command that will execute the program.
command=/path/to/gunicorn --workers=3 --bind=127.0.0.1:8000 app.wsgi:application

; Change directory before executing the "command".
directory=/path/to/project

; Start the program when the system boots.
autostart=true

; Always restart the program when it exits.
autorestart=true

; Define the locations of the log files.
stdout_logfile=/path/to/log.out.log
stderr_logfile=/path/to/log.err.log

; Define custom environment variables that can be accessed inside the app.
; If a string value contains the percent (%) symbol, it must be escaped
; with another percent (%) symbol.
environment=SECRET_KEY="INSERT RANDOM %% STRING HERE %%",CONF="live.conf"
```


Restarting supervisor
--------------------------------------------------
`sudo service supervisor restart`


Using supervisorctl
--------------------------------------------------

#### Running supervisorctl in interactive mode
`supervisorctl`

#### Exit supervisorctl interactive mode
`supervisorctl> exit`

#### List processes
`supervisorctl status`

#### Stopping a process
`supervisorctl stop PROCESS_NAME`

#### Starting a process
`supervisorctl start PROCESS_NAME`

#### Shutting down supervisor
`supervisorctl shutdown`

Check for changes in the configuration file and
run all the changes:

```bash
sudo supervisorctl reread
sudo supervisorctl update
```