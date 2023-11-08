



# Cheatsheet Git

## Definitions


## Configurations


## Basic command



## Setting up remotes

### Why you need to use git remote command

- The git remote command is used to manage remote repositories associated with your local Git repository. It allows you to add, list, rename and delete remote repositories, as well as view information about these repositories. It is essential for establishing connections with other repositories, facilitating collaboration and code synchronization between your local repository and remote repositories.


| Command | Description |
| ------- | ----------- |
| `git remote -v` | List Remote Repositories |
| `git remote rename old_name new_name` | Rename a Remote Repository |
| `git remote remove remote_name` | Remove a Remote Repository |







## Sharing projects
### In this paragraph we wil see orders that will be used to share and post your project 

### Why you need to use the command "git push"
 -The "git push" command is used to send your local changes to a remote repository (such as a Git repository hosted on a server) to share with other collaborators. This updates the remote repository with your latest changes, so others can see and retrieve them. In summary, "git push" pushes your local changes to a remote location so that they are accessible to others
- | `'git push origin [branch name]` | Push a branch to your remote repository |

- | `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
- | `git push` | Push changes to remote repository (remembered branch) |

- | `git push origin --delete [branch name]` | Delete a remote branch |


### Why you need to use the command "git pull"

The "git pull" command retrieves changes from a remote repository (such as a Git repository hosted on a server) and merges them with your local copy of the code. In summary, "git pull" updates your local copy with the latest changes to the remote repository.

- | `git pull` | Update local repository to the newest commit 

- | `git pull origin [branch name]` | Pull changes from remote repository 

- | `git remote add origin ssh://git@github.com/[username]/[repository-name].git` 
 Add a remote repository |
 
- | `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |


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


## Review changes


## Tags


## Cherrypicking

