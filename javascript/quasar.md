Quasar
======


Installation
------------

Install the Quasar CLI.

```bash
npm install -g @quasar/cli

# Install to a different directory.
npm install -g @quasar/cli --prefix=/path/to/directory
```

Usage
-----

Create a new project.

```bash
quasar create MySampleProject
```

Run the new project.

```bash
cd MySampleProject
```

```bash
quasar dev
```

Creating a new layout.

```bash
quasar new layout MyLayout
```

Creating a new page.

```bash
quasar new page MyPage
```

Creating a new store module.

```bash
quasar new store MyStore
```

Upgrade
-------

Check for upgradable packages.

```bash
quasar upgrade
```

Perform the actual upgrade

```bash
quasar upgrade --install
```