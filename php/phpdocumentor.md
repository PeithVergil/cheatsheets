phpDocumentor
=============


Installation
--------------------------------------------------
`composer global require "phpdocumentor/phpdocumentor=[2.*]"`


Using phpDocumentor
--------------------------------------------------

### Options
* **-d** Source directory
* **-t** Output directory
* **-i** Ignore files

A simple example for generating a documentation:

```bash
phpdoc -d [/path/to/source] -t [/path/to/output]
```

Use the `-i` option to ignore files and directories.

```bash
phpdoc -d [/path/to/source] -t [/path/to/output] -i [/path/to/source/tests]
```

Multiple files and directories can be ignored by separating the paths with a comma:

```bash
phpdoc -d [/path/to/source] -t [/path/to/output] -i [/path/to/source/bin,/path/to/source/tests,/path/to/source/vendor]
```

Glob syntax is also recognized:

```bash
phpdoc -d [/path/to/source] -t [/path/to/output] -i "[bin/*,tests/*,vendor/*]"
```