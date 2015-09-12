Redis
=====


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
`src/redis-server`


Running Redis client
--------------------------------------------------
`src/redis-cli`


Shutdown server (inside CLI)
--------------------------------------------------
`SHUTDOWN`


Exit client (inside CLI)
--------------------------------------------------
`quit`


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
