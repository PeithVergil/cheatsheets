Node.js
=======

Installation
--------------------------------------------------

Install the [Node Version Manager](https://github.com/nvm-sh/nvm). Change the version number (v0.33.11) to the latest value.

```shell
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

Display all versions available for installation.

```shell
nvm ls-remote
```

Display all versions available on local computer.

```sh
nvm ls
```

Use `nvm` to install the latest `node` release.

```sh
nvm install node
```

Use `nvm` to install the latest `node` LTS release.

```sh
nvm install --lts
```

Migrate global packages from an old installation to a new installation.

```sh
nvm install node --reinstall-packages-from=v9.4.0
```

Use `nvm` to activate the installed `node`.

```sh
nvm use node
```

Use `nvm` to display the current active version.

```sh
nvm current
```

Display the path of the current active version.

```sh
nvm which v9.4.0
```

Uninstall an old installation.

```sh
nvm uninstall v9.4.0
```

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

Installing packages
--------------------------------------------------

Installing a package to a specific directory.

```sh
npm install -g typescript --prefix=/path/to/directory
```

Uninstalling a package.

```sh
npm uninstall infinite-scroll --save
```

Checking for outdated global packages.

```sh
npm outdated -g --prefix=/path/to/directory
```

Updating global packages.

```sh
npm update -g --prefix=/path/to/directory
```

Change the `npm` prefix
--------------------------------------------------

Create an **npmrc** file in the home directory:
`echo prefix = ~/.node >> ~/.npmrc`

Add the new `npm` prefix to the system **PATH**:
`export PATH=/home/myusername/.node/bin:$PATH`
