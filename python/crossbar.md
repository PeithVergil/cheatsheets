Crossbar WAMP Router
====================


Installation
------------

```bash
pip install crossbar
```

Usage
-----

Creating a new crossbar project:

```bash
# Create a new project directory.
mkdir myproject && cd myproject

# Initialize the project directory.
crossbar init
```

Docker
------

Starting a crossbar instance.

```bash
docker run -it --rm --name crossbar --network wag_services --network-alias wag_crossbar --publish 9000:9000 -v $PWD:/node crossbario/crossbar
```

Running an Autobahn Python project.

```bash
# Create a virtual environment.
docker run -it --rm --name autobahn --network wag_services -v $PWD:/app crossbario/autobahn-python python -m venv py39

# Install Python packages.
docker run -it --rm --name autobahn --network wag_services -v $PWD:/app crossbario/autobahn-python py39/bin/pip install -r requirements.txt

docker run -it --rm --name autobahn --network wag_services -v $PWD:/app crossbario/autobahn-python py39/bin/python -m myproject
```