Neovim
======

Installation
------------

#### Manually adding a PPA source.

Create a new file in `/etc/apt/sources.list.d`. Note the `.list` file extension.

```bash
sudo vi /etc/apt/sources.list.d/neovim.list
```

Add the following lines into the new file and save.

```
deb http://ppa.launchpad.net/neovim-ppa/stable/ubuntu xenial main 
deb-src http://ppa.launchpad.net/neovim-ppa/stable/ubuntu xenial main 
```

Add the PPA key.

```bash
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 9DBB0BE9366964F134855E2255F96FCF8231B6DD
```

Update software sources and install `neovim`.

```bash
sudo apt-get update
sudo apt-get install neovim
```

##############################
# Navigating through text
b # Jump to prev word
w # Jump to next word

gg # Jump to top of file
G  # Jump to end of file

CTRL+b # Page up
CTRL+f # Page down

##############################
# Inserting text
I # Insert at start of the line
A # Insert at end of the line
O # Insert at prev line
o # Insert at next line

##############################
# Copy/cut and paste

v      # Text selection
V      # Line selection
CTRL+v # Column selection

y # Copy selected text
d # Cut selected text

p # paste after the cursor
P # paste before the cursor

##############################
# Joining lines
J
##############################
# Yanking/copy line
yy
##############################
# Delete/cut line
dd

##############################
# Undo
u

##############################
# Redo
CTRL+r

##############################
# Find
?[keyword to find]

n # Find next occurence going forward
N # Find next occurence going backwards

##############################
# Find and replace

# Case sensitive
:%s/[regex search pattern]/[regex replace pattern]/gc

# Case insensitive
:%s/[regex search pattern]/[regex replace pattern]/gci

##############################
# Switching windows
CTRL+ww
