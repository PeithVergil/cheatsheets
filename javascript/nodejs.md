Node.js
=======


Installation
--------------------------------------------------
```bash
sudo apt-get update
sudo apt-get install nodejs npm
```

On Ubuntu, the NodeJS executable is called "nodejs", NPM expects it to be called "node". So, we need to create a symlink like this:

`sudo ln -s /usr/bin/nodejs /usr/bin/node`


Change the `npm` prefix
--------------------------------------------------

Create an **npmrc** file in the home directory:
`echo prefix = ~/.node >> ~/.npmrc`

Add the new `npm` prefix to the system **PATH**:
`export PATH=/home/myusername/.node/bin:$PATH`