# Cheatsheet Git

## Table of content
- [Definitions](#definitions)
- [Aliases](#aliases)
    - [How to set up your aliases](#how-to-set-up-your-aliases)
    - [A few useful aliases](#a-few-useful-aliases)
- [Staging and comiting](#staging-and-commiting)
- [Setting up remotes](#setting-up-remotes)
    - [Why you need to use git remote command](#why-you-need-to-use-git-remote-command)
    - [Working with Remote Repositories](#working-with-remote-repositories)
    - [Branches and Remote Repositories](#branches-and-remote-repositories)
    - [Cloning Remote Repositories](#cloning-remote-repositories)
- [Sharing projects](#sharing-projects)
    - [Why you need to use the command "git push"](#why-you-need-to-use-the-command-git-push)
    - [Why you need to use the command "git pull"](#why-you-need-to-use-the-command-git-pull)
- [Branch and Merge/Rebase](#branch-and-mergerebase)
    - [Branch](#branch)
    - [Merges and Rebase](#merges-and-rebase)
- [Stash](#stash)
- [Logs](#logs)
- [Tags](#tags)
- [Cherrypicking](#cherrypicking)
- [Commit Convention](#commit-convention)




## Definitions
- Repository : a repository tracks and saves the history of all changes 
- Fork : Cloning someone else's repository so that it is on your own github under your name
- Remote : a remote is a repository that isn't local (usually on something like github or gitlab)
- Origin : Your remote repository of a forked project
- Upstream : The _original_ remote repository of a project you forked

![Local/Origin/Upstream schema](https://devopscube.com/wp-content/uploads/2021/02/git-forked-upstream-min.png)




## Aliases
### How to set up your aliases

Aliases are basically shortcut for any command. You can set up whatever aliases you want by following those steps :

1. go into your `.zshrc` using the command `code .zshrc`
2. once inside your file, go all the way to the bottom and add `source ~/.aliases`
3. create `.aliases.sh` into your `~/user directory`
4. in your `.aliases.sh` create your aliases following this syntax :
    - `alias [your alias]="[the command]"` for exemple `alias lz="lazygit"`

If you installed `oh my zsh` you should already have a few aliases installed, just use `aliases` to see a list

### A few useful aliases

- `alias gs="git status"`
- `alias gb="git branch -a"`
- `alias gr="git remote -v"`
- `alias lz="lazygit"`
- `alias gffs="git flow feature start"`
- `alias gfff="git flow feature finish"`




## Staging and commiting

| Command | Description |
| ------- | ----------- |
| `git status` | Check status |
| `git add [file-name.txt]` | Add a file to the staging area |
| `git add -A` | Add all new and changed files to the staging area |
| `git commit -m "[commit message]"` | Commit changes |
| `git rm -r [file name]` | Remove a file (or folder) |




## Setting up remotes
### Why you need to use git remote command

- The git remote command is used to manage remote repositories associated with your local Git repository. It allows you to add, list, rename and delete remote repositories, as well as view information about these repositories. It is essential for establishing connections with other repositories, facilitating collaboration and code synchronization between your local repository and remote repositories.

| Command | Description |
| ------- | ----------- |
| `git remote -v` | List Remote Repositories |
| `git remote rename [old name] [new name]` | Rename a Remote Repository |
| `git remote remove [remote name]` | Remove a Remote Repository |


### Working with Remote Repositories

| Command | Description |
| ------- | ----------- |
| `git fetch [remote name]` | Fetch Changes from a Remote Repository |
| `git pull [remote name] [branch name]` | Pull Changes from a Remote Repository |
| `git push [remote name] [branch name]` | Push Local Changes to a Remote Repository |




### Cloning Remote Repositories

| Command | Description |
| ------- | ----------- |
| `git clone [repository url]` | Clone a Remote Repository (Creates a Local Copy) |
| `git clone [repository url] [local directory name]` | Clone a Remote Repository into a Custom Local Directory |





## Sharing projects
In this paragraph we wil see orders that will be used to share and post your project 

### Why you need to use the command "git push"
The "git push" command is used to send your local changes to a remote repository (such as a Git repository hosted on a server) to share with other collaborators. This updates the remote repository with your latest changes, so others can see and retrieve them. In summary, "git push" pushes your local changes to a remote location so that they are accessible to others

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
| `git remote add origin [repository ssh address]` |Add a remote repository |
| `git remote set-url origin [repository ssh address]` | Set a repository's origin branch to SSH |


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




## Logs 
| Command | Description |
| ------- | ----------- |
| `git log` | Logs in Current Branch|
| `git log -n 5` | Logs last n number of commits |
| `git log branch1..branch2` | Commits between branch1 and branch2 |
| `git remote rename [old name] [new name]` | Commits in branch1 that are not in branch2 |
| `git log branch1 ^branch2` | List Remote Repositories |




## Tags

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
  
| Type          | Description                                              |
|---------------|----------------------------------------------------------|
| **feat**      | Introducing a new feature (feature)                      |
| **fix**       | Fixing a bug                                             |
| **docs**      | Documentation changes                                    |
| **style**     | Code style changes (non-breaking space)                   |
| **refactor**  | Code refactoring (modification that doesn't add features or fix bugs) |
| **perf**      | Performance improvements                                 |
| **test**      | Adding or modifying tests                                |
| **chore**     | Maintenance tasks, minor changes not affecting logic     |
  
More information :

[conventional commits](https://www.conventionalcommits.org/en/v1.0.0-beta.4/#summary)

[Angular commit format](https://github.com/angular/angular/blob/main/CONTRIBUTING.md#-commit-message-format)

