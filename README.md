# Git
### Git

[Git is a free and open source distributed version control system.](http://git-scm.com)

* Install Git

  ```linux
  $ sudo apt-get install git
  ```

* git config

  ```linux
  $ git config --global user.name "name"
  $ git config --global user.email "emailAddress"
  ```



### Create a New Repository

* `git init` 

  to initialize empty Git repository

* `git add/rm <file>...` 

  to update what will be committed

* `git checkout -- <file>...` 

  to discard changes in working directory

* `git reset HEAD <file>...` 

  to unstage

* `git commit -m <message>` 

  to commit

* `git status` 

  to check the status of the repository

* `git diff <file>` or `git diff`



### Manage Versions

* `git log --graph --pretty=oneline --abbrev-commit` or `git log` 

  to check the commits history

* `git reset --hard <commit id>`  

  to go back to a history version

  *e.g.*  `git reset --hard HEAD^` to go back to the last version

* `git reflog` 

  to check the commands history



### Manage Branches

* `git checkout -b <new branch>`

  > or `git branch <new branch>` to create a new branch, then `git checkout <branch>` to switch to the branch

   to switch to a new branch

* `git switch -c <new branch>`

  > `git switch <branch>` to switch to the branch

   to switch to a new branch in a more clear way

* `git branch`

  to check the working branch

* `git merge <another branch>` 

  to merge another branch to the working branch in `Fast-forward` mode

* `git merge --no-ff -m <merge message> <another branch>` 

  to merge by the `Recursive` strategy

* `git branch -d <another branch>` 

  > `git branch -D <another branch>` to delete a branch which is **not** fully merged

  to delete a branch

* `git stash`

  to save the working directory

* `git stash list`

  to check the stash list

* `git stash pop` or `git stash apply` then `git stash drop`

  to recovery the working directory and delete the stash

* `git cherry-pick <commit id>`

  to copy a specific commit to the working branch



### Manage Repositories on GitHub

* Create SSH key in local

  > Check if there exist `id_rsa`, `id_rsa.pub` under `~/.ssh/`. If so, skip. Otherwise, create SSH key. 

  ```linux
  $ ssh-keygen -t rsa -C "emailAddress"
  ```

* Add SSH key on GitHub

  Log in GitHub, "Settings", "SSH and GPG keys", "New SSH key"

* Create a new repository on GitHu

  Log in GitHub, "your repositories", "New"

* `git remote add origin git@github.com:username/repository.git` or `git remote add origin https://github.com/username/repository.git`

  to link an existing repository in local and the new empty one on GitHub

* `git push -u origin master`

  > `-u` for the first time

  to push the existing repository in local to the GitHub

* `git remote -v` or `git remote`

  to check the repository on GitHub

* `git push origin <branch>`

  to push a branch of the repository in local to the GitHub

* `git clone git@github.com:username/repository.git` or `git clone https://github.com/username/repository.git`

  to clone a repository on GitHub into local

* `git checkout -b <branch> origin/<branch>`

  to clone a branch on GitHub and switch to it in local

* If `git push origin <branch>` fail, then `git pull`.
* If `git pull` fail, `git branch --set-upstream-to <local branch> origin/<branch>`  to link the branch in local and the one on GitHub, then `git pull`.



### Manage Tags

* `git tag <new tag>` or `git tag <new tag> <commit id>` or `git tag -a <new tag> -m <tag message> <commit id>`

  to create a tag

* `git tag`

  to check the tag list

* `git show <tag>/<commit id>...`

  to show more details of the tags

* `git push origin <tag>.../--tags`

  to push the tag(s) in local to GitHub

* `git tag -d <tag>...`

  to delete the tag(s) in local

* `git push origin :refs/tags/<tag>...`

  to delete the tag(s) on GitHub, delete the tag(s) in local, then push  



### Tips

* commit only related changes
* commit often
* do **NOT** commit half-done work
* test code before you commit
* wirte good commit message
* version control is **NOT** a backup system
* use branches for new features, bug fixes, ideas...
* agree on a workflow
* help & documentation `$ git help <command>`
