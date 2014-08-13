Git 
===

## Installation
`sudo apt-get install git-core`

## Generate SSH key
`ssh-keygen -t rsa -C "youremail@yourdomain.com"`

## Setting configurations
    git config --global color.ui true
    git config --global core.editor vi
    git config --global user.name "Your Name"
    git config --global user.email "youremail@yourdomain.com"

## Viewing revisions
    git log
    git log --graph


Branches
--------------------------------------------------
#### Merging branches
`git merge --no-ff dev-branch`

#### Creating a new branch
`git branch newbranch` or `git checkout -b newbranch`

#### Creating a tracking branch
`git branch --track newbranch origin/master`

#### Creating a new remote branch
`git push [origin] [mybranch]:[mybranch]`


## Edit the last commit message
`git commit --amend -m "New commit message"`

## Show changes to a commit
`git diff-tree --no-commit-id --name-only -r bd61ad98`

## Set a default remote branch
`git branch --set-upstream master origin/master`


## Update the URL of the remote branch
`git remote set-url origin git://new.url.here`