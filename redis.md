Redis
=====

Redis is an in-memory key-value store.


Installation
--------------------------------------------------

To install redis on Ubuntu:

```bash
sudo apt-get update
sudo apt-get install redis-server
```


Manual Compilation
--------------------------------------------------

Update the repo cache:

```bash
sudo apt-get update
```

Install the build tools:

```bash
sudo apt-get install build-essential
```

Download the source code:

```bash
wget http://download.redis.io/redis-stable.tar.gz
```

Unpack the tar archive then change directory:

```bash
tar xvfz redis-stable.tar.gz
cd redis-stable
```

Start the compilation:

```bash
make
```

Install system-wide:

```bash
sudo make install
```


Configurations
--------------------------------------------------

#### Open config file
`vim /etc/redis/redis.conf`

#### Set values
    port 6379
    bind 127.0.0.1


Compiling from source
--------------------------------------------------

#### Download the source code
`wget http://redis.googlecode.com/files/redis-2.6.13.tar.gz`

#### Extract
`tar xzf redis-2.6.13.tar.gz`

#### Change directory
`cd redis-2.6.13`

#### Compile
`make`

#### Copy server and client
    cp src/redis-server /usr/local/bin
    cp src/redis-cli /usr/local/bin

#### Copy init script
`cp utils/redis_init_script /etc/init.d/redis_6379`

#### Create a directory to store Redis config files and data:
    mkdir /etc/redis
    mkdir /var/redis

#### Copy config file
`cp redis.conf /etc/redis/6379.conf`

#### Create a working directory for the Redis instance
`mkdir /var/redis/6379`

#### Add the new Redis init script to all the default runlevels
`sudo update-rc.d redis_6379 defaults`


Running Redis server
--------------------------------------------------

```bash
src/redis-server
```


Running Redis client
--------------------------------------------------

```bash
src/redis-cli
````


Shutdown server (inside CLI)
--------------------------------------------------

```
SHUTDOWN
```


Exit client (inside CLI)
--------------------------------------------------

```
quit
```


Commands
--------------------------------------------------

#### Set
`SET mykey myvalue`

#### Get
`GET mykey`

#### Delete
`DEL mykey`

#### Increment
    SET mynumber 100
    INCR mynumber


Interacting with `redis` using Python
--------------------------------------------------

Install `redis-py`.

```bash
pip install redis
```

Create a connection. The default host, port, and db is `127.0.0.1`, `6379`, and `0` respectively.

```python
from redis import StrictRedis

r = StrictRedis(host='127.0.0.1', port=6379, db=0)
```

Put an item into the store.

```python
r.set('fname', 'hello')
```

Get an item from the store.

```python
r.get('fname')
```

Put multiple item into the store.

```python
r.mset(fname='hello', lname='world')
```

Get multiple item from the store.

```python
r.mget(['fname', 'lname'])
```

Increment a numeric value by 1.

```python
r.set('age', 1)

r.incr('age')
```

Increment a numeric value by a certain amount.

```python
r.set('age', 1)

r.incrby('age', 20)
```

Check if an item exists.

```python
r.exists('fname')
```

Delete an item from the store.

```python
r.delete('fname')
```

Put an item that will expire after a given time (in seconds).

```python
r.set('user:helloworld', 'you have been banned...')

r.expire('user:helloworld', 5)
```

Put a list item into the store with `lpush`. `lpush` will insert items from the start of the list.

```python
r.lpush('numbers', 1)
r.lpush('numbers', 2)
r.lpush('numbers', 3)
r.lpush('numbers', 4)
r.lpush('numbers', 5)
```

Get a list item from the store.

```python
r.lrange('numbers', 0, -1)
```

Put a list item into the store with `rpush`. `rpush` will insert items from the end of the list.

```python
r.rpush('numbers', 1)
r.rpush('numbers', 2)
r.rpush('numbers', 3)
r.rpush('numbers', 4)
r.rpush('numbers', 5)
```

Get a list item from the store.

```python
r.lrange('numbers', 0, -1)
```

Put a dict item into the store.

```python
r.hmset('user', {'username': 'hello', 'password': 'world'})
```

Get a dict item from the store.

```python
r.hgetall('user')
```

Get a specific key from the dict item.

```python
r.hget('user', 'username')
```