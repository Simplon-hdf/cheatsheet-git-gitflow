
# Cheat Sheets Git Flow  
  
## Introduction to Git Flow  

Git Flow is a branching strategy designed to streamline the development workflow and simplify collaboration among team members in Git-based projects. It was created by Vincent Driessen and has gained widespread adoption in the software development community.  
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/schema%20command%20gitflow/gitflowschema.png" alt="Schemagitflow" width="500"/>
  
## How to initiate Git Flow  
  
```
git flow init
```
  
The git flow init command is used to initialize a new Git repository with Git Flow, which defines a set of branching conventions designed to optimize collaboration, release management, and issue tracking in software development projects.

<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/schema%20command%20gitflow/gitflowinit.png" alt="Schemagitflow" width="500"/>  
  
## Basic command  
  
```
git flow feature start (name)
```  
  
The git flow feature start command is used to create a new feature branch in a Git repository.  
Features in Git Flow are used to develop new functionality or make significant changes to the codebase. Using feature branches helps keep the development work isolated from the main branches (develop and master), allowing teams to work on different features independently.  
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/schema%20command%20gitflow/gitflowfeaturestat.png" alt="Schemagitflow" width="500"/> 
  
---
  
```
git flow feature finish (name)
```  
  
The command git flow feature finish (name) attempts to finish a feature branch named (name) using the Git Flow workflow.  
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/schema%20command%20gitflow/gitflowfeatureFinish.png" alt="Schemagitflow" width="500"/> 
  
---
  
```
git flow release start (1.0.0)
```  
  
When you run this command, Git Flow will create a new release branch based on the current state of the develop branch. You can then use this release branch to prepare for a new software release. Typically, you would use the release branch to fix any remaining bugs, update documentation, and perform other tasks necessary for the release. 
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/schema%20command%20gitflow/GitFlowRealiseStart.png" alt="Schemagitflow" width="500"/> 
  
---
  
```
git flow release finish (1.0.0)
```  
  
When you run this command, Git Flow performs the following actions:  

- Merges changes from the release branch into both the master branch and the develop branch.
- Tags the release with the specified version number (1.0.0 in this case).
- Updates the master branch with the changes made in the release branch.
- Updates the develop branch with the changes made in the release branch.
- Removes the release branch from the repository.
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/160f9641eaba9831fe08543b2fdbd33a399134be/image/GitFlowRealiseFinish.png" alt="Schemagitflow" width="500"/> 
  
---
  
```
git push origin --tags
```  
  
 Git will push all of your annotated tags to the remote repository on the origin remote. This is useful when you want to share your tags with others who might be working on the same project or to backup your tags in a remote repository. 
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/160f9641eaba9831fe08543b2fdbd33a399134be/image/GitPushTags.png" alt="Schemagitflow" width="500"/> 
  
---
  
```
git flow hotfix start (name)
```  
  
This command will create a new hotfix branch based on the latest state of the develop branch. Hotfix branches are used to quickly address critical issues or bugs in the codebase that need to be fixed immediately, even if you are in the middle of working on a feature or a release.
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/160f9641eaba9831fe08543b2fdbd33a399134be/image/GitFlowHotfixStart.png" alt="Schemagitflow" width="500"/> 
  
---
  
```
git flow hotfix finish (name)
```  
  
This command will merge the changes from the hotfix branch into both develop and master branches, tag the release with the hotfix version number, and remove the hotfix branch from your repository.  
   
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/160f9641eaba9831fe08543b2fdbd33a399134be/image/GitFlowHotfixFinish.png" alt="Schemagitflow" width="500"/> 
  
## How to set up aliases  
  
```
alias (alias)="(command)"
```  
This is the command to set up these aliases.  
Here is how I set up my aliases.   
  
```
alias gffs="git flow feature start"  
alias gfff="git flow feature finish"  
alias gfrs="git flow release start"  
alias gfrf="git flow release finish"  
alias gfhs="git flow hotfix start"  
alias gfhf="git flow hotfix finish"  
alias gpot="git push origin --tags"  

```  
  
  You'll need to put them in the .zshrc or .bashrc file, like this.  
    
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/schema%20command%20gitflow/aliasgitflow.png" alt="Schemagitflow" width="500"/>  
  
## Create Workflow in Teams  
  
First, we need to fork the upstream repository into our own origin
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/Fork.png" alt="Schemagitflow" width="500"/>  
  
In the terminal, we will clone using this command. 
   
```
git clone (SSH in origin)
```  

<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/clone.png" alt="Schemagitflow" width="500"/>  
  
And now we can initialize Git Flow.

```
git flow init
```  
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/GitFlowInit2.png" alt="Schemagitflow" width="500"/>  
  
In order to fetch and merge to update our origin and local repositories, we need to set up the remote.  
  
```
git remote add upstream (ssh/https upstream)  
```  
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/remote.png" alt="Schemagitflow" width="500"/>  
  
we work in branch "develop" push the branch dev in origin and create new branch in upstream.  
  
```
git push --set-upstream origin develop
```  

<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/BrancheDevOrigin.png" alt="Schemagitflow" width="500"/>  
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/BrancheDevUpstream.png" alt="Schemagitflow" width="500"/>  
  
We should never work directly on the main branch; we will create the develop branch in both the origin and upstream repositories.
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/Pullrequest.png" alt="Schemagitflow" width="500"/>  
  
After checking the naming convention, make changes to the code before validating the merge.
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/GoodCommit.png" alt="Schemagitflow" width="500"/>  
  
If everything is okay, we can now merge the pull request.
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/Merge.png" alt="Schemagitflow" width="500"/>  
  
Now, in the Upstream repository, the develop branch is up-to-date with your own develop branch. For other colleagues, they can fetch and merge to update their own origin and local repositories.
  
<img src="https://raw.githubusercontent.com/Simplon-hdf/cheatsheet-git-gitflow/develop/image/Workflow%20team/uptodate.png" alt="Schemagitflow" width="500"/>  
  
```
git fetch upstream develop
git merge origin/develop
```  
