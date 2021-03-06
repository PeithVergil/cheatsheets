Mercurial
=========

Installation
--------------------------------------------------
`sudo apt-get install mercurial`


Configuration
--------------------------------------------------

Edit the config file:

```bash
vim ~/.hgrc
```

Add the following lines to the file:

```
[ui]
username = Peith Vergil <peith.vergil@gmail.com>
editor = vim
merge = internal:merge

[extensions]
rebase =
color =
hggit = 
```


Generating an SSH key
--------------------------------------------------
`ssh-keygen -t rsa -C "myemail@example.com"`



#### Creating a repo
    hg init myproject
    hg init


#### Getting the status
    hg status
    hg st


#### Adding files
    hg add myfile0, myfile1, myfile2
    hg add


#### Commiting changes
    hg commit -m "My message here"
    hg commit
    hg ci


#### Showing commits

# Show revision (-r) #3 with patches/diffs (-p)
hg log -p -r 3

# Show revision #3 in verbose mode (full description)
hg log -v -r 3

# Show all revisions
hg log


#### Undoing changes that have not been commited

# Undo changes to one file
hg revert myfile

# Undo changes to all
hg revert --all


#### Undoing the last commit
hg rollback


#### Undoing a specific commit
hg backout -r 3

# Jump to a commit
hg update tip # Jump to latest commit
hg update 1   # Jump to second commit
hg update 0   # Jump to first commit

# Get the current commit number
hg identify -n # Return the commit number
hg identify    # Return the commit ID

# Untrack files from repo
hg forget file0 file1 file2

# Merging heads
hg merge

# Resolve merging conflicts
hg resolve --list       # List the files with conflicts
hg resolve file0
hg resolve --mark file0 # Mark file0 as resolved

# Detect moved/deleted files
hg addremove --similarity 100

# Display the contents of a file
hg cat -r 0 a.txt
hg cat a.txt

# Start server
hg serve


#### Tags

# Adding a tag
hg tag v1.0

# Show all tags
hg tags

# Removing a tag
hg tag --remove v1.0


Bookmarks
--------------------------------------------------

#### List all bookmarks
`hg bookmarks`


#### Creating a bookmark
`hg bookmark [mybookmark]`


#### Renaming a bookmark
`hg bookmark --rename [oldbookmark] [newbookmark]`


#### Deleting a bookmark
`hg bookmark --delete [mybookmark]`


#### Check for incoming bookmarks
`hg incoming -B`


#### Check for outgoing bookmarks
`hg outgoing -B`


#### Pushing a bookmarked changeset
`hg push -B [mybookmark]`


#### Pulling a bookmarked changeset
`hg pull -B [mybookmark]`


#### Pushing a changeset using a bookmark name
`hg push -r [mybookmark]`


#### Pulling a changeset using a bookmark name
`hg pull -r [mybookmark]`


#### Moving a bookmark forward
`hg bookmark [mybookmark] -r [123]`


#### Moving a bookmark backward
`hg bookmark [mybookmark] -f -r [100]`


Rebasing
--------------------------------------------------

**NOTE:** You can only rebase local commits that have not yet been shared to another repo.

Use the `-s` option to select the source changeset. Select the very root of the branch as the source, not the tip. Use the `-d` option to mark the destination changeset.

```bash
hg rebase -s 123 -d 125
```

Collapse changesets while rebasing by passing the `--collapse` option.

```bash
hg rebase -s 123 -d 125 --collapse
```