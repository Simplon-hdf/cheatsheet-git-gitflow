# Cheatsheet Git

## Definitions


## Configurations


## Basic command



## Setting up remotes



## Sharing projects


## Branch and Merge/Rebase
### Branch
| Command | Description |
| ------- | ----------- |
| `git branch` | List branches (the asterisk denotes the current branch) |
| `git branch -a` | List all branches (local and remote) |
| `git branch [branch name]` | Create a new branch |
| `git branch -d [branch name]` | Delete a branch |
| `git branch -m [old branch name] [new branch name]` | Rename a local branch |
| `git push -u [remote name] [branch name]` | Create a remote branch from a local branch and track it|
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git switch [branch name]` | Switch to the branch |

### Merges and Rebase
#### What is the difference between `git merge` and `git rebase` ?

`git merge` : merging looks for two commit pointers (usually the last commit of each branch) and will create a **merge commit** which will combine both ends of each branch into a new commit
`git rebase` : rebasing takes the commits from a source branch and reapplies it onto a target branch

!(Merge vs Rebase)[https://dataschool360.files.wordpress.com/2019/11/e841d-1pzt4kmizdofsmokh-cjjfq.png]

| Command | Description |
| ------- | ----------- |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git rebase [branch name]` | rebase a branch into the active branch |
| `git rebase [source branch] [target branch]` | rebase a branch into a target branch |
| `git rebase -i` | start the interactive rebase |



## Stash


## Review changes


## Tags


## Cherrypicking