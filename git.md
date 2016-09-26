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
    git log --oneline


Remove a file from the repository.

```sh
git rm --cached myfile.txt
```

Remove a directory from the repository.

```sh
git rm --cached -r mydirectory
```


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

#### Renaming a branch
`git branch -m [oldname] [newname]`

#### Renaming the current branch
`git branch -m [newname]`


## Edit the last commit message
`git commit --amend -m "New commit message"`

## Show changes to a commit
`git diff-tree --no-commit-id --name-only -r bd61ad98`

## Set a default remote branch
`git branch --set-upstream master origin/master`


## Add the URL of the remote branch
`git remote add [origin] [git://new.url.here]`

## Update the URL of the remote branch
`git remote set-url [origin] [git://new.url.here]`


Squashing Commits
--------------------------------------------------

Work with the last five commits in the repo. This will launch a text editor where you can edit commands.

```bash
git rebase -i HEAD~5
```

Use the `pick` command to select a commit as the destination. Use the `fixup` command to select commits as sources.

```
pick  a1376af51aac Commit message #1
fixup 60e46b95d13f Commit message #2
fixup aff725a8957b Commit message #3
fixup 43995f662fd3 Commit message #4
fixup 8948e8b6f943 Commit message #5
```

When done, just save and close the text editor. Commits #1 to #5 should now be just a single commit.