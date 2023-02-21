>Виконали студенти групи РПЗ-03  
>Команда 2:
>
>Кушанов Р.Г.  
>Путін М.Г.  
>Штома Д.О.  

### What is git used for, what are the main actions and commands performed in it

`git` - is a version control system used by both large companies and individual software developers. `git` allows you to conveniently save intermediate work results, for quick return to any of the stages of development, or division of labor between different specialists.


Basic commands `git`:

  - `git init` - initializes the repository in the selected folder
  - `git add <file>` - adds the file to the repository
  - `git commit -m"<commit name>"` - creates a new commit
  - `git branch <name>` - creates a new branch
  - `git checkout <branch name>` - sets the `HEAD` pointer to the specified branch
  - `git checkout <commit id>` - sets the `HEAD` pointer to the specified commit
  - `git push <remote repository>` - pushes the current branch to the specified branch in the remote repository
  - `git merge <branch name>` - "glues" the current branch with the one specified in the command, and creates a new commit belonging to the specified branch
  - `git remote add <link>` - tells the current repository the link under which the remote repository is stored
  - `git pull` - a quick command that replaces the alternate execution of the next two commands- 
  - `git fetch <remore branch>` - retrieves the state of the specified remote branch
  - `git merge` - updates the local branch to the pulled state of the remote branch

### What is a "commit" and how does it allow you to track changes to files?

`Commit` is a snapshot of the state of the working tree at a certain point in time. The commit pointed to by `HEAD` becomes its parent when a new commit is created. This means that `git` in the commit saves the changes made on the previous commit (parent).

`Working tree` is any directory on your file system that has a repository associated with it. Includes all files and subdirectories of that directory.

A `repository` is a collection of commits, each of which is an archive of what the project's working tree looked like at some point in the past. It also specifies the head (HEAD), which identifies the branch or commit from which the current working tree branches.
