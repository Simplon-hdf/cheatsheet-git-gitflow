



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

### Working with Remote Repositories

| Command | Description |
| ------- | ----------- |
| `git fetch remote_name` | Fetch Changes from a Remote Repository |
| `git pull remote_name branch_name` | Pull Changes from a Remote Repository |
| `git push remote_name branch_name` | Push Local Changes to a Remote Repository |

### Branches and Remote Repositories

| Command | Description |
| ------- | ----------- |
| `git checkout -b new_local_branch remote_name/remote_branch` | Create a New Local Branch Based on a Remote Branch: |
| `git branch --set-upstream-to=remote_name/remote_branch local_branch` | Set Upstream Branch to Track a Remote Branch Locally |
| `git push remote_name branch_name` | Push Local Changes to a Remote Repository |

### Cloning Remote Repositories

| Command | Description |
| ------- | ----------- |
| `git clone repository_url` | Clone a Remote Repository (Creates a Local Copy) |
| `git clone repository_url local_directory_name` | Clone a Remote Repository into a Custom Local Directory |





## Sharing projects
### In this paragraph we wil see orders that will be used to share and post your project 

### Why you need to use the command "git push"
 -The "git push" command is used to send your local changes to a remote repository (such as a Git repository hosted on a server) to share with other collaborators. This updates the remote repository with your latest changes, so others can see and retrieve them. In summary, "git push" pushes your local changes to a remote location so that they are accessible to others
| Command | Description |
| ------- | ----------- |
| `git push origin [branch name]` | Push a branch to your remote repository |
| `git push -u origin [branch name]` | Push changes to remote repository (and remember the branch) |
| `git push` | Push changes to remote repository (remembered branch) |
| `git push origin --delete [branch name]` | Delete a remote branch |


### Why you need to use the command "git pull"

The "git pull" command retrieves changes from a remote repository (such as a Git repository hosted on a server) and merges them with your local copy of the code. In summary, "git pull" updates your local copy with the latest changes to the remote repository.
| Command | Description |
| ------- | ----------- |
| `git pull` | Update local repository to the newest commit 
| `git pull origin [branch name]` | Pull changes from remote repository 
| `git remote add origin ssh://git@github.com/[username]/[repository-name].git` |Add a remote repository |
| `git remote set-url origin ssh://git@github.com/[username]/[repository-name].git` | Set a repository's origin branch to SSH |


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

| Command | Description |
| ------- | ----------- |
| `git stash`| Temporarily saves changes that are not ready to be committed.|
| `git stash apply`| Applies the latest stash to the working directory.|
| `git stash pop`| Applies and removes the latest stash.|
| `git stash list`| Lists all stashes.|
| `git stash show [stash]`| Show the changes recorded in the stash as a diff between the stashed state and its original parent. When no stash is given, shows the latest one.|
| `git stash drop [stash]`| Remove a single stashed state from the stash list. When no stash is given, it removes the latest one.|
| `git stash clear`| Remove all the stashed states. Note that those states will then be subject to pruning, and may be impossible to recover.|

[More information](https://ndpsoftware.com/git-cheatsheet.html#loc=index;)
## Review changes

## Logs 

### Basic logs 

| Command | Description |
| ------- | ----------- |
| `git log` | Logs in Current Branch|
| `git log -n 5` | Logs last n number of commits |
| `git log branch1..branch2` | Commits between branch1 and branch2 |
| `git remote rename old_name new_name` | Commits in branch1 that are not in branch2 |
| `git log branch1 ^branch2` | List Remote Repositories |



## Tags


### What are tags on git 

- Git tags are fixed landmarks in code history, used to mark stable versions, important landmarks, and project-specific states. They allow you to reference and track software versions, which facilitates the management, navigation and consistent deployment of code.

| Command | Description |
| ------- | ----------- |
| `git tag tag_name` | Create a lightweight tag |
| `git tag -a tag_name -m "Tag message"` | Create an annotated tag with an associated message |
| `git tag` | List all tags in the local repository |
| `git show tag_name` | Display details of a specific tag |
| `git push origin tag_name` | Push a tag to a remote repository |
| `git push --tags` | Push all tags to a remote repository |
| `git tag -d tag_name` | Delete a tag from the local repository |
| `git push --delete origin tag_name` | Delete a tag from the remote repository |



## Cherrypicking

### What is cherry picking

Cherry picking is the act of picking a commit from a branch and applying it to another. Cherry pick can be used in very specific situation such as :
- big hotfixes
- undoing changes and restoring lost commit
- copying a specific piece of code that can be reused somewhere else

| Command | Description |
| ------- | ----------- |
|`git cherry-pick commitSha`|Takes the commit and applies it to your current branch|*

**The Sha is the commit id. He can be identified using the `git log` command*

## Commit Convention

The conventional commit message format is a simple yet powerful convention that enforces consistency in commit messages, making them more informative and easier to understand for both humans and machines.
```
<type>(<scope>): <message>
```

- `<type>`: Describes the purpose of the commit (e.g., feat, fix, chore, docs, style, refactor, test, etc.).
- `<scope>` (optional): Specifies the part of the codebase that the commit affects.
- `<message>`: A short, concise description of the changes.

for example :
```
feat(user-auth): add password reset functionality
```

More information :

[conventional commits](https://www.conventionalcommits.org/en/v1.0.0-beta.4/#summary)

[Angular commit format](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#-commit-message-format)

