# Git-CheatSheet

**Some of mostly used git commands**   

## Configurations

- Define the author *name* and *email* to be used for all commits by the current user.

	```
	        git config --global user.name  <name>
	        git config --global user.email <email>
	```

- Set text editor used by commands for the current user. arg should be the command that launches the desired editor (e.g., nano, code)

	```
	    git config --global core.editor <editor>
	```

- Open the global configuration file in a text editor for manual editing.

	```
	git config --global --edit
	```

## Basics

- Create empty Git repo in specified directory.
-  Run with no arguments to initialize the current directory as a git repository.
	```
	git init [directory]
	```
- Stage all changes  for the next commit.
- ```<args>``` could be any of:
	- ``` .``` , ```--all```   or ``` -A``` add all files from the current directory.
	- ```<list of files>``` add specific files
	- ```<list of directories>``` add all files from specific directories.
	
	
	```
	git add <args>
	```
	
- List which files are *staged*, *unstaged*, and *untracked*.


	```
	git status
	```
	
- Commit the staged snapshot.
- you can use ``` -m <message>``` as the commit message instead of launching a text editor.


	```
	git commit -m <message>
	```
	
	
## Undoing
- Reset staging area to match most recent commit.

	```
	git reset
	```
	
- Remove ```<list of files>``` from the staging area, but leave the working directory unchanged. 
- This unstages files without overwriting any changes.

	```
	git reset <list of files>
	```
	
- Undo the last commit
- there are five modes [ soft, hard, mixed, merge, keep] work as follows:
	- ```--soft``` remove the last commit from the current branch, but the file changes will stay in your working tree, Also the changes will stay on your index.
	- ```--mixed``` the default mode and quite similar to ```--soft```; keep the changes in your working tree but not on the index;
	- ```--hard``` **lose all uncommited changes and all untracked files**
	- ```[ --keep, --merge]``` to be continued.

	``` 
	git reset <mode> head~1
	```
	
## Branching
- List all of the branches in your repo.
-  Add a ```<branch>``` argument to create a new branch with the name ```<branch>```.
	```
	git branch
	```
- Create  and check out a new branch named ```<branch>```.
- Drop the -b flag to checkout an existing branch.
	```
	git checkout -b <branch>
	```
- Renaming a branch you are currently on
	```
	git branch -m <new_branch_name>
	```

## Logging
- Display the entire commit history using the default format.

	```
	git log
	```
	
- Limit number of commits by . E.g. ```git log -5``` will limit to 5 commits.

	```
	git log -<limit>
	```
	
- Condense each commit to a single line.
	
	```
	git log --oneline
	```
	
