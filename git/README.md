# Sharing and updating project 

#### In this paragraph we wil see orders that will be used to share and post your project 

#### Why you need to use the command "git push"
 -The "git push" command is used to send your local changes to a remote repository (such as a Git repository hosted on a server) to share with other collaborators. This updates the remote repository with your latest changes, so others can see and retrieve them. In summary, "git push" pushes your local changes to a remote location so that they are accessible to others
- | `'git push origin [branch name]` | Push a branch to your remote repository |

- | `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
- | `git push` | Push changes to remote repository (remembered branch) |

- | `git push origin --delete [branch name]` | Delete a remote branch |


#### Why you need to use the command "git pull"

The "git pull" command retrieves changes from a remote repository (such as a Git repository hosted on a server) and merges them with your local copy of the code. In summary, "git pull" updates your local copy with the latest changes to the remote repository.

- | `git pull` | Update local repository to the newest commit 

- | `git pull origin [branch name]` | Pull changes from remote repository 

- | `git remote add origin ssh://git@github.com/[username]/[repository-name].git` 
 Add a remote repository |
 
- | `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |
