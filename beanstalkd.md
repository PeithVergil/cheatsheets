beanstalkd
==========


Installation
--------------------------------------------------

Install using the Ubuntu package manager.

```bash
sudo apt-get install beanstalkd
```


Service Management
--------------------------------------------------

Start the service.

```bash
service beanstalkd start
```

Stop the service.

```bash
service beanstalkd stop
```

Restart the service.

```bash
service beanstalkd restart
```

Check for the status.

```bash
service beanstalkd status
```


Interacting with `beanstalkd` using Python
--------------------------------------------------

Install `beanstalkc`.

```bash
pip install pyyaml
pip install beanstalkc
```

Create a connection. The default host and port is `0.0.0.0` and `11300`.

```python
from beanstalkc import Connection

beanstalk = Connection(host='127.0.0.1', port=11300)
```

Put a new job in the queue.

```python
beanstalk.put('This is your job...')
```

Fetch a job from the queue.

```python
job = beanstalk.reserve()
```

Delete a job when done.

```python
job.delete()
```

Select a job queue. Selecting a job queue for the first time creates it.

```python
beanstalk.use('notifications')
```

Check the current selected job queue.

```python
beanstalk.using()
```

List all job queues.

```python
beanstalk.tubes()
```

Display stats about the `beanstalkd` process.

```python
from pprint import pprint

pprint(beanstalk.stats())
```