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

Use a different SSH key.

```bash
git config core.sshCommand "ssh -i /path/to/sshkey -F /dev/null"
```

Add remote URL.

```bash
git remote add origin https://github.com/USERNAME/REPOSITORY.git
git push -u origin master
```

Change remote URL.

```bash
git remote set-url origin https://github.com/USERNAME/REPOSITORY.git
```

## Viewing revisions
    git log
    git log --graph
    git log --oneline
    git log --reverse

Show the list of files that was changed for a certain commit.

```bash
git show --name-only 6df7741679461bebe013d5d94d2ce5d841a9d9ad
```

Remove a file from the repository.

```sh
git rm --cached myfile.txt
```

Remove a directory from the repository.

```sh
git rm --cached -r mydirectory
```

## Renaming a tracked file

```sh
git mv /path/to/file.txt /path/to/newfile.txt
```


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

Delete a local branch.

```sh
git branch -d mybranch
```

Delete a remote branch.

```sh
git push origin :mybranch
```

Fetching a remote branch.

```sh
git fetch origin remote-branch
```

The fetched `remote-branch` will be stored in FETCH_HEAD. Create a new branch from `FETCH_HEAD`.

```sh
git checkout -b new-branch FETCH_HEAD
```

Cloning a specific remote branch.

```sh
git clone -b [mybranch] [git://new.url.here]
```

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


Tagging
--------------------------------------------------

**Options:**
| Option | Description                          |
|:------:|:------------------------------------:|
| **-a** | Create an annotated tag.             |
| **-m** | A message stored with the tag.       |
| **-l** | List tags matching wildcard pattern. |

Creating a **lightweight** tag. A lightweight tag is just a pointer to a specific commit.

```bash
git tag v1.2.3b
```

Creating an **annotated** tag. An annotated tag is stored as a full object containing the tagger name, email, date, message, etc.

```bash
git tag -a v1.2.3 -m "This is version 1.2.3"
```

Display all tags.

```bash
git tag
```

Display tags that match a given wildcard pattern.

```bash
git tag -l "v1.*"
```

Show details about a particular tag.

```bash
git show v1.2.3
```

Delete a tag.

```bash
git tag -d v1.2.3b
```

#### Workflows

Archiving a branch.

```bash
git tag archive/PT-150 feature/PT-150
git branch -d feature/PT-150
git checkout master
```


Rebasing
--------------------------------------------------

To rebase one branch onto another, select the branch that will be moved.

```bash
git checkout source-branch
```

Then, rebase the selected branch to another.

```bash
git rebase target-branch
```


Undoing Commits
--------------------------------------------------

Undo the last commit and never see it again.

```bash
git reset --hard HEAD~1
```

Undo the last commit but keep the changes.

```bash
git reset HEAD~1
```


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