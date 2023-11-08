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
| `git push origin --delete [branch name]` | Delete a remote branch |
| `git switch [branch name]` | Switch to the branch |

### Merges and Rebase
| Command | Description |
| ------- | ----------- |
| `git merge [branch name]` | Merge a branch into the active branch |
| `git merge [source branch] [target branch]` | Merge a branch into a target branch |
| `git rebase [branch name]` | rebase a branch into the active branch |
| `git rebase [source branch] [target branch]` | rebase a branch into a target branch |
| `git rebase -i` | start the interactive rebase |



## Stash

The *stash* is a place where you can temporarily shelves (or stashes) changes you've made to your working copy so you can work on something else, and then come back and re-apply them later on
<img src="https://scaler.com/topics/images/options-in-git-stash.webp">
|Command|uses|
|:---------|:------|
| ` git stash`| Temporarily saves changes that are not ready to be committed.|
| ` git stash apply`| Applies the latest stash to the working directory.|
| ` git stash pop`| Applies and removes the latest stash.|
| ` git stash list`| Lists all stashes.|
| ` git stash show [stash]`| Show the changes recorded in the stash as a diff between the stashed state and its original parent. When no stash is given, shows the latest one.|
| ` git stash drop [stash]`| Remove a single stashed state from the stash list. When no stash is given, it removes the latest one.|
| ` git stash clear`| Remove all the stashed states. Note that those states will then be subject to pruning, and may be impossible to recover.|

[More information](https://ndpsoftware.com/git-cheatsheet.html#loc=index;)
## Review changes


## Tags


## Cherrypicking