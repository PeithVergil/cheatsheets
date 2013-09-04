Git Cheatsheet
==============

### Installation
`sudo apt-get install git-core`

### Generate SSH key
`ssh-keygen -t rsa -C "your_email@youremail.com"`

### Setting configurations
    git config --global color.ui true
    git config --global core.editor vi
    git config --global user.name "Peith Vergil"
    git config --global user.email "peith.vergil@gmail.com"

### Viewing revisions
`git log --graph`

### Merging branches
`git merge --no-ff dev-branch`

### Edit the last commit message
`git commit --amend -m "New commit message"`

### Show changes to commit
`git diff-tree --no-commit-id --name-only -r bd61ad98`
