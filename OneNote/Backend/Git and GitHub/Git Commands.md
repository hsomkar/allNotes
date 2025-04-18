Here are the Git commands which are being covered:

- **git config**
- **git init**
- **git clone**
- **git add**
- **git commit**
- **git diff**
- **git reset**
- **git status**
- **git rm**
- **git log**
- **git show**
- **git tag**
- **git branch**
- **git checkout**
- **git merge**
- **git remote**
- **git push**
- **git pull**
- **git stash**

So, let's get started!

## **Git Commands**

### git config

Usage: git config –global user.name “[name]”    
Usage: git config –global user.email “[email address]”    
This command sets the author name and email address respectively to be used with your commits.

![Git Config Command - Git Commands - Edureka](Exported%20image%2020250408212435-0.png)

### git init

Usage: git init [repository name]  
This command is used to start a new repository.

![GitInit Command - Git Commands - Edureka](Exported%20image%2020250408212437-1.png)

### git clone

Usage: git clone [url]    
This command is used to obtain a repository from an existing URL.

![Git Clone Command - Git Commands - Edureka](Exported%20image%2020250408212442-2.png)

### git add

Usage: git add [file]    
This command adds a file to the staging area.

![Git Add Command - Git Commands - Edureka](Exported%20image%2020250408212443-3.png)

Usage: git add *  
This command adds one or more to the staging area.

![Git Add Command - Git Commands - Edureka](Exported%20image%2020250408212450-4.png)

### git commit

Usage: git commit -m “[Type in the commit message]”  
This command records or snapshots the file permanently in the version history.

![Git Commit Command - Git Commands - Edureka](Exported%20image%2020250408212452-5.png)

Usage: git commit -a    
This command commits any files you’ve added with the git add command and also commits any files you’ve changed since then.

![Git Commit Command - Git Commands - Edureka](Exported%20image%2020250408212454-6.png)

### git diff

Usage: git diff   
This command shows the file differences which are not yet staged.

![Git Diff Command - Git Commands - Edureka](Exported%20image%2020250408212456-7.png)

 Usage: git diff –staged  
This command shows the differences between the files in the staging area and the latest version present.

![Git Diff Command - Git Commands - Edureka](Exported%20image%2020250408212458-8.png)

Usage: git diff [first branch] [second branch]    
This command shows the differences between the two branches mentioned.

![Git Diff Command - Git Commands - Edureka](Exported%20image%2020250408212500-9.png)

### git reset

Usage: git reset [file]    
This command unstages the file, but it preserves the file contents.

![Git Reset Command - Git Commands - Edureka](Exported%20image%2020250408212506-10.png)

Usage: git reset [commit]    
This command undoes all the commits after the specified commit and preserves the changes locally.

![Git Reset Command - Git Commands - Edureka](Exported%20image%2020250408212511-11.png)

Usage: git reset –hard [commit]  This command discards all history and goes back to the specified commit.

![Git Reset Command - Git Commands - Edureka](Exported%20image%2020250408212513-12.png)

### git status

Usage: git status    
This command lists all the files that have to be committed.

![Git Status Command - Git Commands - Edureka](Exported%20image%2020250408212515-13.png)

### git rm

Usage: git rm [file]    
This command deletes the file from your working directory and stages the deletion.

![Git Rm Command - Git Commands - Edureka](Exported%20image%2020250408212517-14.png)

### git log

Usage: git log    
This command is used to list the version history for the current branch.

![Git Log Command - Git Commands - Edureka](Exported%20image%2020250408212518-15.png)

Usage: git log –follow[file]    
This command lists version history for a file, including the renaming of files also.

![Git Log Command - Git Commands - Edureka](Exported%20image%2020250408212520-16.png)

### git show

Usage: git show [commit]  
This command shows the metadata and content changes of the specified commit.

![Git Show Command - Git Commands - Edureka](Exported%20image%2020250408212523-17.png)

### git tag

Usage: git tag [commitID]    
This command is used to give tags to the specified commit.

![Git Tag Command - Git Commands - Edureka](Exported%20image%2020250408212528-18.png)

### git branch

Usage: git branch  
This command lists all the local branches in the current repository.

![Git Branch Command - Git Commands - Edureka](Exported%20image%2020250408212530-19.png)

Usage: git branch [branch name]    
This command creates a new branch.

![Git Branch Command - Git Commands - Edureka](Exported%20image%2020250408212532-20.png)

Usage: git branch -d [branch name]    
This command deletes the feature branch.

![Git Branch Command - Git Commands - Edureka](Exported%20image%2020250408212534-21.png)

### git checkout

Usage: git checkout [branch name]    
This command is used to switch from one branch to another.

![Git Checkout Command - Git Commands - Edureka](Exported%20image%2020250408212537-22.png)

Usage: git checkout -b [branch name]    
This command creates a new branch and also switches to it.

![Git Checkout Command - Git Commands - Edureka](Exported%20image%2020250408212538-23.png)

### git merge

Usage: git merge [branch name]    
This command merges the specified branch’s history into the current branch.

![Git Merge Command - Git Commands - Edureka](Exported%20image%2020250408212540-24.png)

### git remote

Usage: git remote add [variable name] [Remote Server Link]    
This command is used to connect your local repository to the remote server.

![Git Remote Command - Git Commands - Edureka](Exported%20image%2020250408212546-25.png)

### git push

Usage: git push [variable name] master  
This command sends the committed changes of master branch to your remote repository.

![Git Push Command - Git Commands - Edureka](Exported%20image%2020250408212548-26.png)

Usage: git push [variable name] [branch]    
This command sends the branch commits to your remote repository.

![Git Push Command - Git Commands - Edureka](Exported%20image%2020250408212551-27.png)

Usage: git push –all [variable name]    
This command pushes all branches to your remote repository.

![Git Push Command - Git Commands - Edureka](Exported%20image%2020250408212555-28.png)

Usage: git push [variable name] :[branch name]    
This command deletes a branch on your remote repository.

![Git Push Command - Git Commands - Edureka](Exported%20image%2020250408212600-29.png)

### git pull

Usage: git pull [Repository Link]    
This command fetches and merges changes on the remote server to your working directory.

![Git Pull Command - Git Commands - Edureka](Exported%20image%2020250408212602-30.png)

### git stash

Usage: git stash save    
This command temporarily stores all the modified tracked files.

![Git Stash Command - Git Commands - Edureka](Exported%20image%2020250408212604-31.png)

Usage: git stash pop    
This command restores the most recently stashed files.

![Git Stash Command - Git Commands - Edureka](Exported%20image%2020250408212609-32.png)

Usage: git stash list    
This command lists all stashed changesets.

![Git Stash Command - Git Commands - Edureka](Exported%20image%2020250408212614-33.png)

Usage: git stash drop    
This command discards the most recently stashed changeset.

![Git Stash Command - Git Commands - Edureka](Exported%20image%2020250408212616-34.png)

Want to learn more about git commands? Here is a [Git Tutorial](https://www.edureka.co/blog/git-tutorial/) to get you started. Alternatively, you can take a top-down approach and start with this [DevOps Tutorial.](https://www.edureka.co/blog/devops-tutorial)
