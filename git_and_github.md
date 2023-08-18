Git is a software that allows you to keep track of changes made to a project over time. Git works by recording the changes you make to a project, storing those changes, then allowing you to reference them as needed.

## 1. Basic Workflow

```Bash
Workflow
git init - Sets up all the tools Git needs to begin tracking changes (initialize)
git add - Files are (added) ready for commit (moves from working to staging area)
	git add . - add every file in the working directory to the staging area
	. - all files
git commit - changes from staging are saved to the repository as a commit
	git commit -m "message describing the commit" 
	message be in "", present tense, and brief (<=50 characters)

Helpers
git status - checks the status of the project (commits and untracked files)
git diff - check the differences between the working directory and the staging area
git log - view chronological commits in the repository
	SHA - 40-character code the ids the commit 
	commit author, date, and message
```

 A Git project can be thought of as having three parts:
1. A _Working Directory_: where you’ll be doing all the work: creating, editing, deleting and organizing files (Additions, Deletions, Modifications) 
2. A _Staging Area_: where you’ll list changes you make to the working directory 
3. A _Repository_: where Git permanently stores those changes as different _versions_ of the project 

working > staging > repository
init > add > commit

- The Git workflow consists of editing files in the working directory, adding files to the staging area, and saving changes to a Git repository.

- Untracked means that Git sees the file but has not started tracking changes yet
---

# 2. Important Operations

Backtracking - eraser-like features that allow us to undo mistakes during project creation.
HEAD (commit) - The commit you are currently on 

```Shell
git show HEAD - show the changes made to the commit 
git checkout HEAD filename - Discards changes in the working directory.
	git checkout -- filename = git checkout HEAD filename
	checkout = working directory
git reset HEAD filename - Unstages file changes in the staging area.
	M - modification
	reset = staging area
git reset commit_SHA - Resets to a previous commit (based on 7 char SHA)
```

## Note to self - re-review backtracking "I understand it but need more practice"

- Use reset in essence rewinds the projects history to the 7 char SHA of your choice
- it’s common to change many files, add those files to the staging area, and [commit](https://www.codecademy.com/resources/docs/git/commit) them to a repository in a single commit.

## Handy Git Operations

```Shell 
stash
git stash - allows you to get back to a clean commit point with a synchronized working tree, and avoid losing your local changes in the process
	You’re “stashing” your local work temporarily inorder to update a previous commit
git stash pop - retrieve the code you were working on that was stored/stashed

log 
git log --oneline - shows the list of commits in one line format.
git log -S "keyword" - displays a list of commits that contain the keyword in the message
git log --oneline --graph - Displays a visual representation of how the branches and commits were created in order to help you make sense of your repository histor

amend
git commit --amend - it allows you to correct mistakes and edit commits easily
	Git actually does is replace the whole previous commit.
	git commit --amend --no-edit - if you dont want to updated your -m message

aliases
git config --global alias.co "checkout"
git config --global alias.br "branch"
```
---

3. This is a fake edit
4. This is another fake edit (8/17/23) 