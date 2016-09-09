Node.js
=======


Installation
--------------------------------------------------

To install `nodejs` using the Ubuntu package manager:

```sh
sudo apt-get install nodejs npm
```

To install the latest `nodejs` from PPA, update packages the repository.

```sh
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
```

Then, install `nodejs` and `npm`:

```sh
sudo apt-get install nodejs
```

**This step might be optional.** On Ubuntu, the executable is called **nodejs**, but `npm` expects it to be **node**. So, we need to create a symbolic link like this:

```sh
sudo ln -s /usr/bin/nodejs /usr/bin/node
```


Change the `npm` prefix
--------------------------------------------------

Create an **npmrc** file in the home directory:
`echo prefix = ~/.node >> ~/.npmrc`

Add the new `npm` prefix to the system **PATH**:
`export PATH=/home/myusername/.node/bin:$PATH`