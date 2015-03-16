Bower
=====


Installation
--------------------------------------------------

Install `bower` globally using NPM:
```bash
npm install -g bower
```


Search for packages
--------------------------------------------------

An example for using `bower` to search for specific packages:

```bash
bower search backbone
bower search knockout
```

This will list all available Bower packages:

```bash
bower search
```


Installing packages
--------------------------------------------------

An example for using `bower` to install packages:

```bash
bower install backbone
bower install knockout
```

Installing a specific version of a package:

```bash
bower install jquery#1.7.0
```


Uninstalling packages
--------------------------------------------------

An example for using `bower` to uninstall packages:

```bash
bower uninstall jquery
```


Updating packages
--------------------------------------------------

Update all packages to their latest version:

```bash
bower update
```


Listing packages
--------------------------------------------------

List all installed packages:

```bash
bower list
```

Show the repo URL of a package:

```bash
bower lookup backbone
```

Show available versions of a package:

```bash
bower info backbone
```


Clear cache
--------------------------------------------------

Remove all cached packages in `~/.bower`

```bash
bower cache-clean
```