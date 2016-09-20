rsync
=====

Options
-------

**-a** - archive (recursive)
**-n** - dry-run
**-r** - recursive
**-v** - verbose
**-z** - compress files


Usage
-----

Sync to a local destination:

```bash
rsync -av source_directory/ destination_directory
```

**NOTE:** Include the trailing slash on the source directory.

Sync (push) to a remote destination:

```bash
rsync -av source_directory/ username@remotehost:destination_directory
```

Sync (pull) from a remote destination:

```bash
rsync -av username@remotehost:source_directory/ destination_directory
```

Delete files in destination directory if they have been deleted from source directory.

```bash
rsync -av --delete username@remotehost:source_directory/ destination_directory
```