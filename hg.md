Mercurial
=========

Installation
--------------------------------------------------
`sudo apt-get install mercurial`


Configuration (~/.hgrc)
--------------------------------------------------

#### Set username
[ui]
username = Peith Vergil <peith.vergil@gmail.com>

#### Enable extensions
[extensions]
color =
hggit = 


Generating an SSH key
--------------------------------------------------
`ssh-keygen -t rsa -C "myemail@example.com"`


####################################
### Creating a repo
hg init myproject
hg init


####################################
### Getting the status
hg status
hg st

####################################
### Adding files
hg add myfile0, myfile1, myfile2
hg add

####################################
### Commiting changes
hg commit -m "My message here"
hg commit
hg ci

####################################
### Showing commits

# Show revision (-r) #3 with patches/diffs (-p)
hg log -p -r 3

# Show revision #3 in verbose mode (full description)
hg log -v -r 3

# Show all revisions
hg log

####################################
### Undoing changes that have not been commited

# Undo changes to one file
hg revert myfile

# Undo changes to all
hg revert --all

####################################
### Undoing the last commit
hg rollback

####################################
### Undoing a specific commit
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

####################################
### Tags

# Adding a tag
hg tag v1.0

# Show all tags
hg tags

# Removing a tag
hg tag --remove v1.0
